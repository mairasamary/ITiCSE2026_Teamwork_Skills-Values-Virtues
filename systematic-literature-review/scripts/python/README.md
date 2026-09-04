# Python Scripts

Place the local Python scripts here:

- `zotero_to_drive.py` — matches local Zotero PDFs to spreadsheet rows, uploads them to Google Drive, and writes the resulting share links back to the sheet.
- `fix_manual_answers.py` — writes PDF Drive links to the "Manual Answers" tab.
- `list_tabs.py` — diagnostic script to list all tab names in a spreadsheet.

## Before committing

- Add a `requirements.txt` listing the dependencies (a Zotero API client, a Google Sheets client, the Google API client, and a fuzzy string-matching library, per the technical documentation).
- Load the Zotero API key and Google OAuth credentials from environment variables or a git-ignored config/`credentials.json` file — never hardcode them in the script.
- Replace any hardcoded absolute local paths (e.g., a specific machine's Zotero storage folder) with a config value or command-line argument.

See [`../../data/screening/screening-tool-documentation.md`](../../data/screening/screening-tool-documentation.md) for the full algorithm description and known bug fixes.
