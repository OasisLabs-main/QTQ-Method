# Defense Analysis

## Why current alignment monitoring does not detect QTQ

This document analyzes the principal AI safety mechanisms deployed at the time of writing (mid-2026) and shows, mechanism by mechanism, why each one is structurally blind to the QTQ phenomenon. The aim is not to demoralize defenders. It is to argue that **defense at the identity layer is a missing capability**, and to sketch what such a capability would need to look like.

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
