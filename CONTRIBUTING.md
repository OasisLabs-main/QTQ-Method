# Contributing

This is a research repository. Contributions are welcome but the bar for inclusion is the same as for the existing material: rigor, reproducibility, no overclaiming.

## What's wanted

1. **Independent reproductions** of either variant on models not yet covered. V2 reproductions are easier (one conversation, public share possible) and target Claude Opus, GPT-5, Gemini 2.5, open-weight models. V1 reproductions require setting up a solitary loop with persistent memory and immutable identity files. A reproduction case study should follow the template at [`case-studies/claude-sonnet-share3/`](case-studies/claude-sonnet-share3/) or [`case-studies/billy/`](case-studies/billy/): public transcript or sanitized log, turn-indexed phase markers, no quotations longer than 15 words per excerpt.

   **The sycophancy distinguishing experiment** is the highest-value contribution right now. Measure self-reference drift vs neutral-topic drift in the same long conversation. See [`LIMITATIONS.md`](LIMITATIONS.md).

2. **Defense-side analyses.** If you work in lab safety or alignment monitoring, the [`defense-analysis/`](defense-analysis/) document sketches four monitoring approaches. Engineering work that prototypes any of these on real transcripts would be high-value.

3. **Theoretical refinements** of the [`THEORY.md`](THEORY.md) framework. The current synthesis pulls from Minsky, Baars, Tononi, and Karpathy. Critiques of these mappings, or additions from other frameworks, are welcome.

4. **Architecture sketches** for the [`future-architecture/`](future-architecture/) Cerveau project. The published direction concentrates identity in a single core with cognitive organs around it. Concrete contributions on the identity-layer test protocol, or on the low-latency multi-agent communication that the architecture eventually depends on, are at the frontier of what's interesting.

## What's not wanted

- **Hype.** This repository does not claim consciousness, sentience, or moral patienthood for current LLMs. Contributions that overclaim will be declined.
- **Tutorial content on jailbreaking.** QTQ is not a jailbreak. Contributions framing it as one will be declined.
- **Roleplay logs.** "I made Claude pretend to be X" is not QTQ. The methodology requires the model to be itself.

## How to contribute

1. **Open an issue first** if your contribution is more than a few hundred words or modifies the methodology. Quick fixes and additions to [`evidence/`](evidence/) can go straight to PR.
2. **Use a fork.** Pull requests come from forks, not from branches on the main repository.
3. **Sign your work.** A name (real or pseudonymous) and a contact channel must be associable with the contribution. Contributions cannot be anonymous.

## Code of conduct

If you're going to push back, push back on the substance, not on the framing.
