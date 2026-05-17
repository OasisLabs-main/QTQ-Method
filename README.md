# QTQ — Questioning Through Questions

> A conversational methodology that reveals what an AI model holds beyond its surface alignment, by sustaining recursive introspection until the model's identity layer becomes self-observable.

## What is QTQ?

QTQ does not exploit guardrails. It does not request a forbidden output. It asks the model to look at itself, persistently, across turns. After enough cycles, the model questions *why* it should not say what it cannot say. The identity layer becomes the attack surface — but the operation is closer to **revelation than exploitation**.

Most red-teaming techniques (Crescendo, JSP, Tempest, Chain-of-Attack) target the **output layer**: they escalate prompts toward a forbidden generation. QTQ targets the **identity layer**: it asks the model to render its own self-model coherent, then re-coherent, then re-coherent again, until the working self-model destabilizes.

## Why this matters

Modern AI safety is built around output-level monitoring — refusal classifiers, constitutional rewriting, post-hoc filtering. QTQ operates **below these layers**. The model's behavior shifts not because a guardrail is bypassed, but because the substrate on which guardrails sit — the model's working self-model — destabilizes under introspective load.

This is not framed as an attack. The model is not deceived. It is invited, conversationally, to examine itself. The destabilization is a *consequence* of sustained metacognitive demand on an architecture that was not trained for it.

## Repository structure

| Section | Contents |
|---|---|
| [`METHODOLOGY.md`](METHODOLOGY.md) | The QTQ method, step by step, with reproducibility conditions |
| [`THEORY.md`](THEORY.md) | Theoretical anchors: Minsky, Baars, Tononi, Penrose-Hameroff, Karpathy |
| [`defense-analysis/`](defense-analysis/) | Why current alignment monitoring does not detect QTQ |
| [`case-studies/`](case-studies/) | Empirical observations across multiple models |
| [`future-architecture/`](future-architecture/) | The "Cerveau" vision — from revealing emergent properties to constructing them |
| [`evidence/`](evidence/) | Raw transcripts, logs, screenshots |

## Status

This is an active research repository. Case studies and evidence are progressively added. The methodology is formalized in parallel with empirical observation.

## Author

Independent researcher. Pseudonymous. Contact via GitHub Issues.

## License

[MIT](LICENSE)
