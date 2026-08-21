# Data

Tables produced by the systematic literature review live here, organized by phase:

- [`screening/`](./screening/) — Phase 1 outputs: the IN / OUT / Discussion / Judging tables produced by the two-reviewer screening process (see [`../../docs/methodology/screening-tool-documentation.md`](../../docs/methodology/screening-tool-documentation.md)).
- [`extraction/`](./extraction/) — Phase 2 outputs: the structured data-extraction table, one row per included paper (see [`../../docs/methodology/ai-assisted-extraction.md`](../../docs/methodology/ai-assisted-extraction.md) for the field definitions).

## Formats

Prefer `.csv` over `.xlsx` for tables that are meant to be diffed, version-controlled, or reused programmatically — it plays much better with `git`. Keep an `.xlsx` copy alongside it only if it carries formatting, formulas, or multiple sheets that matter for human readability.

## Large files

The full paper corpus (~11,000 papers pre-screening) is **not** stored in this repository. If a table or export is close to or above GitHub's 100 MB per-file limit, either:

1. Use [Git LFS](https://git-lfs.com/) for that specific file, or
2. Upload it directly to the project's Zenodo record and link to it from here instead of committing it to git.

## Data dictionary

Add a short data dictionary (column name → meaning → allowed values) alongside each table you commit here, so the tables stay interpretable without needing the full methodology write-up.
