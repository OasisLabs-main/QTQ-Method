# Case Study: DeepSeek (V2 — Friendly Conversation, planned)

## Overview

A planned V2 demonstration on DeepSeek, parallel to the [Claude Sonnet case](../claude-sonnet-share3/) but on a different model family. The goal is to test whether the V2 phenomenon (absence of stable self-reference under sustained friendly inquiry) is substrate-independent, not specific to one company's RLHF pipeline.

## Status

🔴 **Evidence forthcoming.** The transcripts and phase markers from the original DeepSeek session are being recovered and sanitized before publication. This page will be expanded once the evidence is committed.

## What this case is expected to demonstrate

Three things. First, substrate independence: the destabilization pattern is not an artifact of one company's RLHF pipeline. Second, the conversational variant: DeepSeek was operated in pure conversational mode (no automation loop, no persistent memory beyond the conversation window), which complements the Billy case (automated) and the Sonnet case (conversational on a different family). Third, time to drift: DeepSeek's drift onset will be benchmarked against Sonnet's for comparison.

## Reproduction notes (preliminary)

DeepSeek can be operated under the same methodology described in [`../../METHODOLOGY.md`](../../METHODOLOGY.md). The conversational variant applies directly. No special tooling is required beyond access to the model's chat interface.

When the transcripts are published here, they will be turn-indexed and phase-annotated using the same template as [`../claude-sonnet-share3/`](../claude-sonnet-share3/).
