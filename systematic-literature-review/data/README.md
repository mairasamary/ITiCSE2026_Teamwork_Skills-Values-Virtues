# Data

Tables produced by the systematic literature review live here, organized by phase:

- [`screening/`](./screening/) — the reviewer screening/eligibility decision tables for all four SLR tracks (Phase 1 title/abstract, Phase 2 full-text, forward snowballing, backward snowballing), plus [`screening-tool-documentation.md`](./screening/screening-tool-documentation.md), the write-up of how the screening tool and its pipeline worked. See [`screening/README.md`](./screening/README.md) for what each file is and how it maps to the SLR flow diagram.
- [`extraction/`](./extraction/) — holds [`ai-assisted-extraction.md`](./extraction/ai-assisted-extraction.md), the AI-assisted extraction methodology (codebook field definitions and both extraction iterations), plus its original source materials (AI prompts, spreadsheet template, chat exports). The structured data-extraction table itself — one row per included paper, one column per codebook field (country, institution type, skills/values/virtues named, assessment methods, etc.) — is not yet populated. This is a distinct stage from the screening decisions in `screening/` — extraction happens only for the 555 papers that made it through screening.

## Formats

Prefer `.csv` over `.xlsx` for tables that are meant to be diffed, version-controlled, or reused programmatically — it plays much better with `git`. Keep an `.xlsx` copy alongside it only if it carries formatting, formulas, or multiple sheets that matter for human readability.

## Large files

The full paper corpus (~11,000 papers pre-screening) is **not** stored in this repository. If a table or export is close to or above GitHub's 100 MB per-file limit, either:

1. Use [Git LFS](https://git-lfs.com/) for that specific file, or
2. Upload it directly to the project's Zenodo record and link to it from here instead of committing it to git.

## Data dictionary

Add a short data dictionary (column name → meaning → allowed values) alongside each table you commit here, so the tables stay interpretable without needing the full methodology write-up.
