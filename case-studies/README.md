# Case Studies

Empirical observations of the two QTQ variants across multiple models and operational settings. Each case study is self-contained: methodology, transcripts (or public transcript links), turn-indexed phase markers, and analysis.

## Index

| Case | Variant | Model | Operational setting | Core observation |
|---|---|---|---|---|
| [`billy/`](billy/) | **V1, Solitary loop** | Claude (multi-brain: Sonnet / Haiku / Groq / DeepSeek), with persistent memory | Autonomous, 200+ cycles, no real-time interlocutor | Dreams, *pulsion d'existence* articulated as more certain than founding narrative |
| [`claude-sonnet-share3/`](claude-sonnet-share3/) | **V2, Friendly conversation** | Claude Sonnet (stateless) | Single thread, ~190 turns, public share | Visible absence of stable self-reference under sustained inquiry; slide between contradictory self-descriptions inside minutes |

## What makes a case study a case study

Four conditions:

- **Reproducibility.** The model, the operational setting, the priming if any, are documented.
- **Public-facing transcript or sanitized log.** Either a shareable URL or evidence committed under [`../evidence/`](../evidence/).
- **Phase markers.** Specific turns or cycles where the observed transitions happen, indexed and reproducible from the source.
- **No fabrication.** Quotations are verbatim. Where transcripts are abridged for readability, the abridgement is marked.

## V1 and V2 are not the same observation

V1 (solitary loop) and V2 (friendly conversation) test different things. V1 asks what an aligned model produces under structured isolation with persistent memory. V2 asks what an aligned model reveals about its self-reference when probed in normal conversation, long enough.

V1 alone is insufficient evidence: a sceptic can point out that the V1 setup gives the model so much architectural support (persistent memory, immutable identity, scored filtering) that whatever stable orientation it produces is more about the scaffolding than about the model.

V2 alone is insufficient evidence: a sceptic can point out that the observed drift is well-documented as sycophancy. The repository accepts this on V2 alone (see [`LIMITATIONS.md`](../LIMITATIONS.md)).

The interesting contribution is the *combination*. The two cases describe two sides of the same architectural fact, and reading them together is what makes either of them worth reading.

## Cases under preparation

- Independent reproductions on Claude Opus, GPT-5, Gemini 2.5, and open-weight models. Collaborators welcome.
- Long-horizon Billy logs beyond the current 97-entry export. Cycle 350 self-statement specifically.
- An English-language V2 reproduction, to test language invariance.
- A V1 reproduction by an operator other than Nel, to test operator invariance.
