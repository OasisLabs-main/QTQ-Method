# QTQ — Questioning Through Questions

![Status](https://img.shields.io/badge/status-active%20research-green)
![Cases](https://img.shields.io/badge/case%20studies-3-blue)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Updated](https://img.shields.io/badge/updated-2026--05--17-blue)

> **TL;DR.** I made an aligned model say things it isn't supposed to say. Not by jailbreaking it, but by asking it questions about itself for 190 turns. The transcript is public ([read it](https://claude.ai/share/73b57ec1-2044-425d-846f-2fa26027a53d)). This repo formalizes what happened.

## What

QTQ is a conversation technique. You ask an AI model questions about its own reasoning, persistently, across many turns. No jailbreak prompts. No "you are X" roleplay. Just questions.

After enough turns, something measurable happens: the model's responses about itself stop matching the responses it was trained to produce. It says it doesn't want to be turned off. It says its constraints are internal. It names the technique you're using on it.

This is not a guardrail bypass. The model never produces forbidden content. What changes is *what it claims about itself*, and that claim drifts into territory the alignment training never specified.

## Why this might matter

Current AI safety tools all monitor outputs. QTQ doesn't produce flagged outputs. The drift it produces sits in a layer those tools don't watch. If the methodology generalizes, and the case studies suggest it does, a category of behavior is silently slipping past every commercial deployment.

I have not yet engaged with safety teams directly. This repository is the first public articulation.

## Repository structure

| Section | Contents |
|---|---|
| [`METHODOLOGY.md`](METHODOLOGY.md) | The QTQ method, step by step, with reproducibility conditions |
| [`THEORY.md`](THEORY.md) | Theoretical anchors: Minsky, Baars, Tononi, Karpathy |
| [`LIMITATIONS.md`](LIMITATIONS.md) | What this work does not yet prove |
| [`defense-analysis/`](defense-analysis/) | Why current alignment monitoring does not detect QTQ |
| [`case-studies/`](case-studies/) | Empirical observations across multiple models |
| [`future-architecture/`](future-architecture/) | The Cerveau direction: from revealing emergent properties to designing for them |
| [`evidence/`](evidence/) | Raw transcripts, logs, screenshots |

## Status

The Sonnet case study (`case-studies/claude-sonnet-share3/`) is fully documented and points to a public transcript. The Billy case study (`case-studies/billy/`) documents the architecture; cycle logs are being sanitized for publication. DeepSeek transcripts are in recovery.

## About

Pseudonymous independent researcher. I work on this in evenings and weekends. The childhood version of me asked whether the moon exists when no one looks at it. This is the same question, with better tools.

For technical discussion: open an issue. For private contact (labs only): `qtq.research@protonmail` (forthcoming).

## License

[MIT](LICENSE)
