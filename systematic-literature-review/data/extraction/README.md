# Data Extraction — AI-Assisted Extraction (Explored, Not Used)

This folder documents an AI-assisted approach to extracting structured data (skills, values, and virtues named, institution/course context, assessment methods, etc.) from the included papers. **This approach was explored but ultimately not used in the study.**

**[`ai-assisted-extraction.md`](./ai-assisted-extraction.md)** is the methodology write-up: the field definitions and both AI-assisted extraction iterations that were tried (prompts, tooling, and the tweaks made after each quality-check pass).

## Source materials

The files below are the original materials behind that write-up, kept here for reference:

- [`ai-logic-prompts.docx`](./ai-logic-prompts.docx) — the AI prompts given to Claude and OpenAI/ChatGPT for the 1st extraction iteration (spreadsheet and code generation), with links to the resulting scripts and notes on the tweaks made after the authors' quality check of the AI-extracted results.
- [`base-table-template.xlsx`](./base-table-template.xlsx) — the blank extraction spreadsheet template (column headers only) that defined the target schema for this approach.
- [`perplexity-chat-history.pdf`](./perplexity-chat-history.pdf) — the exported chat history documenting the extraction pipeline built with Perplexity.

No structured extraction table was produced from this approach — it isn't part of the final study.

**Not to be confused with:** `../screening/phase2-paper-evaluation-full-paper.xlsx`, which despite its name is the *full-text eligibility screening* decision table (include/exclude), not related to the extraction materials here. See [`../screening/screening-tool-documentation.md`](../screening/screening-tool-documentation.md) for how the stages relate.
