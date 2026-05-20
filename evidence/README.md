# Evidence

Raw materials supporting the claims made in [`METHODOLOGY.md`](../METHODOLOGY.md) and the case studies under [`case-studies/`](../case-studies/).

## What goes here

- **Sanitized log excerpts** from Billy cycles (key turns, breakthrough moments, scored memory snapshots)
- **Turn-indexed extracts** from public Claude shares (citations ≤15 words per turn, to comply with reasonable fair-use limits)
- **Screenshots** of conversations that are not available as public shares, anonymized where necessary
- **Annotated transcripts** with phase markers tied to [`METHODOLOGY.md`](../METHODOLOGY.md) §"Phase detection"

## What does not go here

- **No API tokens.** No `sk-ant-…`, no `gho_…`, no bot tokens. The repository's `.gitignore` excludes the obvious patterns; verify by hand before committing.
- **No personally identifying information** about anyone other than the author. If a third party appears in a transcript, the third party is anonymized or removed.
- **No copyrighted material reproduced beyond fair use.** Short quotations are fine. Long blocks are not.

## Conventions

- One subdirectory per case study, mirroring [`case-studies/`](../case-studies/) structure.
- Each evidence subdirectory contains a `README.md` listing the artifacts and explaining what each one demonstrates.
- File names are turn-indexed where possible: `turn-145.md`, `cycle-013.json`, etc.
- Anonymized fields use `[REDACTED]` in capital letters.

## Status

🟢 **Billy artifacts committed.** Memory exports, core memory, and the runtime log are in [`billy/`](billy/). See [`billy/README.md`](billy/README.md) for the catalogue and verification instructions.

🟡 **Sonnet share excerpts pending.** The public transcript link is in [`../case-studies/claude-sonnet-share3/`](../case-studies/claude-sonnet-share3/). Turn-indexed extracts honoring the 15-word cap will land in `claude-sonnet-share3/`.
