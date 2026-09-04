# Data Extraction

**[`ai-assisted-extraction.md`](./ai-assisted-extraction.md)** is the methodology write-up for this stage: the codebook field definitions and both AI-assisted extraction iterations (prompts, tooling, and the tweaks made after each quality-check pass).

## Source materials

The files below are the original materials behind that write-up:

- [`ai-logic-prompts.docx`](./ai-logic-prompts.docx) — the AI prompts given to Claude and OpenAI/ChatGPT for the 1st extraction iteration (spreadsheet and code generation), with links to the resulting scripts and notes on the tweaks made after the authors' quality check of the AI-extracted results.
- [`base-table-template.xlsx`](./base-table-template.xlsx) — the blank extraction spreadsheet template (column headers only) that defines the target schema for the AI-assisted extraction.
- [`perplexity-chat-history.pdf`](./perplexity-chat-history.pdf) — the exported chat history documenting the extraction pipeline built with Perplexity.

## The extraction table itself

*Placeholder — not yet populated.* Once the SVV data-extraction pass is complete, place the structured extraction table here: one row per included paper (of the 555 papers included in the SLR — see [`../screening/README.md`](../screening/README.md)), one column per codebook field, following the field definitions in [`ai-assisted-extraction.md`](./ai-assisted-extraction.md).

Suggested file: `codebook-extraction.csv` (plus an `.xlsx` copy if needed for formatting).

**Not to be confused with:** `../screening/phase2-paper-evaluation-full-paper.xlsx`, which despite its name is the *full-text eligibility screening* decision table (include/exclude) — a different, earlier stage from the data-extraction codebook table that belongs here. See [`../screening/screening-tool-documentation.md`](../screening/screening-tool-documentation.md) for how the stages relate.
