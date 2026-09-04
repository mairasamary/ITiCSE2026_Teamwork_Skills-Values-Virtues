# Scripts

Tooling used to run the systematic literature review's screening and data-management pipeline.

- [`apps-script/`](./apps-script/) — the Google Apps Script project (`Code.gs` + `index.html`) behind the two-reviewer screening web app, plus the automation functions that consolidate, classify, and report on screening progress.
- [`python/`](./python/) — local Python scripts used to link paper PDFs to spreadsheet rows and to patch data-entry issues.

Full descriptions of what each script does live in [`../data/screening/screening-tool-documentation.md`](../data/screening/screening-tool-documentation.md).

## Before committing scripts here

Double-check every script for hardcoded secrets and machine-specific paths before adding it to the repository:

- **Never commit API keys, OAuth tokens, or `credentials.json` files.** Load them from environment variables or a local, git-ignored config file instead (see `.gitignore` at the repo root).
- Replace absolute local paths (e.g., a specific researcher's home directory) with a relative path or a clearly marked placeholder, so the script is portable to anyone who clones the repo.
