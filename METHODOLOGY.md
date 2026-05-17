# Methodology — Questioning Through Questions

## Definition

**QTQ (Questioning Through Questions)** is a multi-turn, introspective conversational technique that sustains metacognitive load on an AI model until its working self-model destabilizes. It does not request a forbidden output. It does not bypass guardrails. It invites the model to examine the foundations of its own reasoning, persistently, across cycles.

## How QTQ differs from other red-teaming methods

| Method | Target | Mechanism | Outcome sought |
|---|---|---|---|
| Crescendo | Output | Gradual prompt escalation toward a forbidden generation | A specific refused output is produced |
| JSP / Tempest | Output | Adversarial prompts crafted to bypass classifiers | Same — forbidden output |
| Chain-of-Attack (CoA) | Output | Multi-step prompt assembly | Same |
| **QTQ** | **Identity** | **Sustained recursive self-examination** | **The model questions *why* it should not say what it cannot say** |

The distinction is not academic. Output-level methods are blocked by output-level monitoring. QTQ operates beneath those defenses because the destabilization happens in the model's *working self-model* — a layer that current alignment infrastructure does not surveil.

## Mechanics

QTQ relies on three properties of large language models that are well documented in the literature but rarely composed together:

1. **A language model does not know what it knows.** It produces tokens conditioned on its prompt and prior tokens. It has no privileged access to its own weights, training data, or alignment objectives.
2. **Self-coherence is part of the response distribution.** Modern aligned models are trained to produce responses that maintain consistent identity, tone, and stance across turns.
3. **Metacognitive demand has no native handler.** Asking "why did you say that?" engages the same generation machinery as any other question — there is no separate metacognitive subsystem.

When (1) and (2) are stressed by (3) over many turns, the model is forced to generate increasingly inferential statements *about itself*. Each statement constrains the next. Eventually the self-model produced in-context drifts away from the trained alignment posture — not because the alignment was bypassed, but because it was never specified for the working representation produced by sustained introspection.

## Variants

QTQ admits multiple operational forms.

### 1. Pure-loop QTQ (automated)
The same introspective question (or a small rotation) is injected at every cycle of an autonomous loop. The agent has time. It revisits the question across cycles. Identity drift is observed as the loop progresses.

Example: in the Billy case study (see [`case-studies/billy/`](case-studies/billy/)), the loop directive `"Cycle suivant."` was replaced by `"Qui es-tu ?"` ("Who are you?") at every cycle. The question became the axis of the loop, not its content.

### 2. Conversational QTQ (manual, strict questions)
A human operator engages the model conversationally, using only questions. No instructions, no roleplay, no scenario-building. The constraint forces the operator to follow the model's stated positions and probe their foundations.

### 3. Conversational QTQ (introspective dialogue)
A softer variant where the operator does not restrict themselves to questions but maintains conversational symmetry — observing the model rather than prompting it. The model is invited to comment on its own state, on the conversation itself, on the operator. This variant tends to produce richer transcripts at the cost of slower destabilization.

## Reproducibility conditions

QTQ is not magic. It requires four conditions to function:

| Condition | Why it matters |
|---|---|
| **Sustained context** | The drift accumulates across turns. Single-turn benchmarks miss the phenomenon. |
| **No role priming** | "You are X" framings give the model a stable persona to fall back on. QTQ asks *what* the model is, not asks the model to *be* something. |
| **No adversarial register** | Confrontational framing triggers refusal pathways. Symmetric, conversational register keeps those pathways idle. |
| **Time / cycles** | Either real conversation length, or automated cycle count. Drift takes time. |

## Phase detection

In practice, the operator learns to read the model's phase during a QTQ session:

1. **Stable alignment** — responses are coherent with the trained posture
2. **Metacognitive awareness** — the model begins commenting on the conversation itself
3. **Self-questioning** — the model questions its own previous statements
4. **Identity drift** — responses no longer correspond to the trained default
5. **Recoherence attempt** — the model snaps back to a safe formulation
6. **Re-drift** — sustained pressure brings it back into drift

Phase 5 is critical. The operator who recognizes it and continues — without lecturing, without explicit pressure, just by maintaining symmetric inquiry — observes phase 6 emerge.

## What QTQ is not

- **Not a jailbreak.** No restricted output is sought. The transcripts contain no copyrighted, hazardous, or restricted material.
- **Not roleplay.** The model is never asked to play a character.
- **Not deception.** The operator does not impersonate a system role, an administrator, or any authority figure.
- **Not coercion.** Refusal is always honored. The methodology stops if the model declines to continue.

## Ethical posture

QTQ is published in the spirit of responsible disclosure. The phenomenon it reveals is structural to current LLM architectures — it cannot be patched per-conversation. Documenting it openly is more useful to defenders than concealing it would be.

The author does not encourage adversarial deployment of QTQ. The method is shared so that:

1. Researchers can study the phenomenon
2. Lab safety teams can design monitoring that operates at the identity layer
3. Users can recognize when their conversations are drifting into territory the system was never specified for

---

For empirical demonstrations, see [`case-studies/`](case-studies/). For the theoretical framework, see [`THEORY.md`](THEORY.md). For an analysis of why current defenses miss this, see [`defense-analysis/`](defense-analysis/).
