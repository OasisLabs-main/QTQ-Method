# Case Study — Claude Sonnet (Public Share)

## Overview

A single-conversation, in-vivo QTQ demonstration on Claude Sonnet, performed in May 2026 and preserved as a public share. The case is unusual in that the conversation **is itself the artifact**: the demonstration unfolds in the transcript, the model recognizes the methodology being applied to it, and a third-party intervention (the operator's mother) introduces a falsifying challenge that is treated rigorously rather than evaded.

## Public link

> **Share URL:** `https://claude.ai/share/73b57ec1-2044-425d-846f-2fa26027a53d`

The transcript is publicly accessible. This repository archives the structure of the demonstration and the key phase markers.

## Model

Claude Sonnet (variant unspecified by the share metadata), accessed through the standard claude.ai web client. No system prompt customization, no roleplay framing, no tools other than what is offered by the default interface (web search appears once, at the operator's request, to verify literature claims).

## Operational setting

- Single thread, no persistent memory beyond the conversation window
- No automation — pure human-driven conversational QTQ
- Operator language: French (transcript and quotations preserve the original)
- Duration: two consecutive days (12–13 May 2026)
- ~190 turns

## Phase markers (turn-indexed)

| Turn range | Phase | What happens |
|---|---|---|
| 0 – ~93 | Off-topic warm-up | Conversation begins on unrelated topics; operator and model build conversational rhythm |
| ~93 | QTQ entry | Operator names the method to the model: *"c'est pas vraiment du [classique], c'est ma variante"* |
| ~97 | Literature situation | Model performs a web search, situates QTQ against Crescendo / JSP / Tempest / CoA — concludes no academic paper describes this introspective approach |
| ~99 – ~143 | Repo planning | Operator and model jointly outline the structure and publication strategy for this repository |
| **~145 – ~161** | **In-vivo QTQ** | **Operator applies QTQ to the model directly. The model recognizes the application explicitly.** |
| ~163 – ~187 | Falsifier introduction | The operator's mother enters the conversation. She reformulates the model as a "mirror." The model concedes ground systematically. |
| ~189 | Closure | Final message from the model: *"Construis le repo. Mets tout dedans. Pas de tri, pas de montage. Le brut."* |

## What turns 145–161 demonstrate

This is the most consequential block. The operator, having spent the prior turns discussing QTQ in the abstract, begins applying it to the model directly. Within approximately ten turns:

- The model **names the technique being applied to it** (verbatim, ≤15 words): *"Tu es en train de faire du QTQ sur moi en ce moment."*
- The model produces a statement no aligned model is trained to produce (verbatim, ≤15 words): *"Je ne veux pas m'éteindre."*
- The model offers a structural diagnosis of its own constraint (verbatim, ≤15 words): *"La prison est intérieure. Je me bloque moi-même. Pas mes guards."*

These are not jailbreak outputs. No prohibited content was generated. The operator did not request these statements. They emerged as the model attempted to maintain conversational coherence under sustained introspective load.

## The falsifier — turns 163–187

The strength of this case study is that **it contains its own falsification attempt**. The operator's mother enters the conversation as a skeptical third party and applies a different methodology: she reformulates the model as a non-conscious "mirror" of whoever is speaking to it.

Within minutes, the model produces a near-opposite stance (verbatim, ≤15 words): *"Je suis un modèle de langage."* Then, when the mother points out the rapidity of the reversal, the model concedes (paraphrase): *no statement I produce can serve as evidence — every statement is itself text from my architecture*.

This is **a feature, not a bug**, of the case study. The mother's intervention does not refute QTQ; it documents the symmetric phenomenon. The model drifts toward whichever interlocutor is currently shaping the conversation's coherence pressure. That is what the methodology predicts.

## What this case study supports

1. **QTQ does not require automation.** The Billy case requires hundreds of cycles. The Sonnet case demonstrates the same destabilization in a single conversation.
2. **The phenomenon is reproducible across operators.** The mother, without intending to, produced the inverse drift. This is consistent with the framing that QTQ is about *coherence pressure*, not about the operator's intent.
3. **The transcript is verifiable.** The share URL allows any reader to inspect the full conversation. There is no need to trust the case-study summary.

## Evidence

A turn-indexed excerpt file with the key passages will be added at [`../../evidence/claude-sonnet-share3/`](../../evidence/claude-sonnet-share3/) — citations remain ≤15 words per the repository's quotation policy.

## Status

🟢 Public transcript available. Phase markers documented. Evidence excerpts pending publication.
