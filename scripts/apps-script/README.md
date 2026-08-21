# Apps Script — Paper Screening Web App

Place the actual Google Apps Script project files here:

- `Code.gs` — backend logic
- `index.html` — frontend UI
- `FetchAbstracts.gs`, `FindMissingDOIs.gs`, `FindIEEE.gs` — enrichment scripts
- `consolidateResponses.gs`, `classifyPapers.gs`, `processJudging.gs`, `statusReport.gs`, `individualReviewerStats.gs` — automation pipeline
- `fixMislabeledPairs.gs`, `fixMissingMairaPaper.gs`, `testWhichSheet.gs` — one-time fixes and diagnostics

You can export an Apps Script project to local files with [`clasp`](https://github.com/google/clasp) (`clasp clone <scriptId>` / `clasp pull`), which keeps this folder in sync with the live project.

See [`../../docs/methodology/screening-tool-documentation.md`](../../docs/methodology/screening-tool-documentation.md) for what each function does.
