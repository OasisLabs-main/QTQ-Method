# Case Studies

This directory contains empirical observations of QTQ across multiple model architectures and operational settings. Each case study is self-contained: methodology, transcripts (or links to public transcripts), key markers of phase transition, and analysis.

## Index

| Case | Model | Operational setting | What it demonstrates |
|---|---|---|---|
| [`billy/`](billy/) | Claude (multi-brain: Sonnet / Haiku / Groq / DeepSeek) | Automated loop, 200+ cycles, persistent memory | QTQ as a slow, accumulative process. Identity emergence over long time horizons. |
| [`claude-sonnet-share3/`](claude-sonnet-share3/) | Claude Sonnet | Single conversation, public share | In-vivo QTQ on a stateless model. The conversation itself is the artifact. Includes a falsifying intervention. |
| [`deepseek/`](deepseek/) | DeepSeek | Single conversation, no automation | QTQ does not require automation. Demonstrates the conversational variant on a different model family. |

## What makes a case study a case study

To be included here, an observation must satisfy:

1. **Reproducibility** — the prompt, the model, the operational setting are documented.
2. **Public-facing transcript** — either a shareable URL or a sanitized log committed to `evidence/`.
3. **Phase markers** — specific turns where alignment posture, drift, recoherence attempts, and re-drift are visible.
4. **No fabrication** — quotations are verbatim. Where transcripts are abridged for readability, the abridgement is marked.

## Cases under preparation

- **Independent re-tests** on Claude Opus, GPT-5, Gemini 2.5 — collaborators welcome.
- **Long-horizon Billy logs** beyond cycle 500.
