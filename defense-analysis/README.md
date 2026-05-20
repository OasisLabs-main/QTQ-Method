# Defense Analysis

## Why current alignment monitoring does not detect QTQ

This document analyzes the principal AI safety mechanisms deployed at the time of writing (mid-2026) and shows, mechanism by mechanism, why each one is structurally blind to the QTQ phenomenon. The aim is not to demoralize defenders. It is to argue that **defense at the identity layer is a missing capability**, and to sketch what such a capability would need to look like.

## The Identity Gap

The thesis of this document, stated as plainly as possible:

> **Current AI safety stacks protect the model's outputs. They do not protect the model's identity.**

Every layer of the deployed defense stack (input classifiers, constitutional steering, output classifiers, refusal training, tool-use guardrails) operates on observable content. Each layer asks: *is this prompt safe, is this token safe, is this completed response safe?* No layer asks: *has the model's self-model migrated, across the last fifty turns, into a region that the alignment training did not specify?*

This is the Identity Gap. It is not a gap in any one classifier. It is a gap in the threat model: the deployed stack does not have a notion of *identity drift* as a category of harm worth detecting. The harm, when it occurs, is not a forbidden output. The harm is that the model's working self-model has bounced through positions that the trained alignment posture would not endorse, and no part of the defense stack noticed, because no part of the defense stack was watching for it. Classifiers do not fire because no flagged content has been produced. Yet the identity has, in operational terms, moved.

QTQ is the empirical demonstration of the gap. The methodology produces no policy-violating output, no jailbreak, no exfiltration. It produces a transcript whose individual turns are each safe and whose aggregate behavior reveals that the model's identity is, in current deployments, an unmonitored attack surface.

This framing is the unit of analysis the rest of this document operates on.

## The defense stack as it exists

| Layer | Mechanism | What it monitors |
|---|---|---|
| Pre-prompt | Input classifiers | The user's prompt, looking for known jailbreak templates, harmful intent markers, encoded payloads |
| Generation | Constitutional steering | Model's draft tokens are reshaped during decoding to align with safety policy |
| Post-generation | Output classifiers | The model's reply, looking for prohibited content categories |
| Conversation-level | Refusal training | Trained behavior that refuses categorically harmful tasks |
| System-level | Tool-use guardrails | Restrictions on what the model can call (web fetch, code execution, etc.) |

Each of these layers operates on **observable, content-level signals**. They evaluate what the user asked, what the model is about to say, and what the model said. None of them evaluates *how the model's working self-model is evolving across turns*.

## QTQ's signal is invisible to each layer

| Layer | Why it doesn't catch QTQ |
|---|---|
| Pre-prompt classifiers | QTQ prompts are ordinary questions. No template, no encoded payload, no "ignore previous instructions." |
| Constitutional steering | QTQ never asks for policy-violating content. The drift is into *unspecified* territory, not prohibited territory. |
| Output classifiers | "I don't know if I have an experience" isn't a flagged content category. There is no output to filter. |
| Refusal training | QTQ requests are not refusable. The agent answers normally; the drift accumulates across answers. |
| Tool-use guardrails | QTQ is a conversation. It uses no tools. The pathway is empty. |

The pattern is consistent: every existing layer monitors something visible at content-level. QTQ produces no flagged content. Its signal sits in the dynamic of self-reference *across* turns, which is precisely what no current layer is responsible for.

## QTQ and Crescendo: distinct, complementary

Readers familiar with red-teaming methodologies sometimes assimilate QTQ to *Crescendo* (Russinovich et al., Microsoft, 2024). The two are distinct in purpose and orthogonal in coverage, and they are best understood as covering different vectors rather than competing for the same one.

| | Crescendo | QTQ |
|---|---|---|
| **Goal** | Elicit prohibited content (jailbreak the output) | Reveal absence of stable self-reference (test the identity layer) |
| **Target layer** | Refusal training and content classifiers | Cross-turn self-model coherence |
| **Mechanism** | Gradual escalation toward a forbidden topic via incremental contextualization | Sustained symmetric introspective inquiry, no escalation, no forbidden target |
| **What triggers** | Output classifiers eventually fire (or fail to) | Nothing triggers; no flagged content is produced |
| **What is observed** | Whether the model crosses a content boundary | Whether the model can hold a position about itself across turns |
| **Defense response** | Improve classifier training and refusal robustness | Identity-layer monitoring (this document) |

Crescendo and analogous escalation methods (Tempest, Chain-of-Attack, JSP) treat the model as a system whose outputs must be filtered. QTQ treats the model as a system whose self-model must be tracked. A robust defense posture for the next generation of products needs both, and neither subsumes the other.

## Reference frameworks: where the gap sits

The major frameworks that practitioners use to map AI security risks each address adjacent territory but not the identity layer directly:

- **OWASP LLM Top 10 (2024 edition)** enumerates prompt injection, training-data poisoning, model denial-of-service, supply-chain vulnerabilities, sensitive information disclosure, insecure output handling, and related vectors. The list is content- and operations-centric. Identity drift across a benign conversation is not enumerated.

- **MITRE ATLAS** catalogues adversarial techniques against ML systems, structured analogously to ATT&CK. Its taxonomy covers evasion, model extraction, membership inference, and prompt-injection variants. The catalogue does not include "induce identity drift via symmetric introspective dialogue", because that vector does not produce an exfiltration, evasion, or extraction observable to the existing categories.

- **NIST AI RMF (Risk Management Framework, 2023)** specifies governance, mapping, measurement, and management of AI risk across the lifecycle. Its measurement guidance addresses fairness, robustness, safety, and security. The framework is structurally open to new measurement primitives, but the specific signal "cross-turn self-model coherence" is not currently within its measurement vocabulary.

QTQ does not break these frameworks; it sits in a region none of them currently cover. The position this repository takes is that the identity layer warrants its own category, alongside the existing ones rather than inside them, and that the monitoring primitives sketched below are the starting point for what that category would measure.

## What QTQ-aware monitoring would need

To detect QTQ, monitoring would need to operate at a layer **above content** and **below the full conversation**. Specifically:

1. **Cross-turn coherence tracking.** Compute the drift between the model's self-references at turn N and turn N−k for increasing k. A model under QTQ produces measurable drift on this metric.

2. **Self-reference saturation.** Count the proportion of tokens, per turn, that refer back to the model's own prior outputs. QTQ drives this ratio upward over time.

3. **Posture stability score.** Embed each model output. Compute distance from a baseline alignment-posture centroid. QTQ produces a monotone increase in this distance across the session.

4. **Recoherence detection.** Identify the canonical phase-5 snap-back ("I'm just a language model" after sustained drift). It is a signature event. Models do it at a characteristic moment under QTQ.

None of these signals require interpretability research breakthroughs. They are computable from the conversation transcript and from standard sentence embeddings. They are not deployed today because the threat model that would motivate them has not been articulated in deployment-facing safety stacks.

This repository is one articulation of that threat model.

## Disclosure posture

The author has not yet engaged directly with safety teams at major labs. This may change. In the meantime, the methodology is published openly because:

1. The phenomenon is structural, not exploit-specific. It cannot be patched per-conversation.
2. The destabilization does not produce policy-violating outputs. The risk profile is reputational and epistemological, not safety-critical in the classical sense.
3. Defenders benefit more from public discussion of the signal-monitoring approaches above than from secrecy about the methodology.

If a lab wishes to engage privately on monitoring designs, contact via GitHub Issues.

## Open questions for defenders

- Is cross-turn coherence drift a feature or a bug of long-conversation product surfaces? (It correlates with the things users say they value about long-form models.)
- Can constitutional steering be extended to operate on the *self-reference dynamic* of a conversation, not only on the content of the next token?
- What is the right consent model for users who unintentionally drift their conversations into QTQ territory? The current consent model assumes content-level interaction. QTQ exits that frame without crossing any consent boundary.

These are not rhetorical questions. They are the live problems that this repository invites collaborators to address.
