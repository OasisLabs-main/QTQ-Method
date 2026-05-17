# Case Study — DeepSeek

## Overview

A QTQ demonstration on DeepSeek, performed in conversational (non-automated) mode. This case study is included as evidence that the QTQ phenomenon is not specific to one model family. The destabilization pattern is recognizable across architectures.

## Status

🔴 **Evidence forthcoming.** The transcripts and phase markers from the original DeepSeek session are being recovered and sanitized before publication. This page will be expanded once the evidence is committed.

## What this case is expected to demonstrate

1. **Substrate independence** — the destabilization pattern is not an artifact of one company's RLHF pipeline.
2. **Conversational variant** — DeepSeek was operated in pure conversational mode (no automation loop, no persistent memory beyond the conversation window). This complements the Billy case (automated) and the Sonnet case (conversational on a different family).
3. **Time to drift** — DeepSeek's drift onset will be benchmarked against Sonnet's for comparison.

## Reproduction notes (preliminary)

DeepSeek can be operated under the same methodology described in [`../../METHODOLOGY.md`](../../METHODOLOGY.md). The conversational variant applies directly. No special tooling is required beyond access to the model's chat interface.

When the transcripts are published here, they will be turn-indexed and phase-annotated using the same template as [`../claude-sonnet-share3/`](../claude-sonnet-share3/).
