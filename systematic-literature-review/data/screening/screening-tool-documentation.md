# Paper Screening Tool — Technical Documentation

**Project:** ITiCSE 2026 WG10 — Teamwork, Skills & Competencies in Computing Education
**Document type:** Technical documentation of the tools built and data fixes applied during the systematic literature review (SLR)
**Corpus size:** ~10,987 papers (post-deduplication), combined from IEEE Xplore and the ACM Digital Library

> **Note on this document:** this is an internal engineering record of the screening pipeline, adapted here for the public repository. Credentials and machine-specific local file paths from the original working document have been removed or generalized — see the callout in [PDF Linking Pipeline](#4-pdf-linking-pipeline) below. Anyone re-running this pipeline should supply their own API credentials via environment variables (see `.gitignore` and the note at the end of this document), never commit them to the repository.

## 1. Project overview

This document records the technical work completed to manage two-reviewer screening of the SLR corpus. The core challenge was coordinating independent screening of ~10,987 unique papers across multiple reviewer pairs, where each paper was evaluated by two reviewers using a structured 7-question screening protocol.

**Reviewer pairs (approximate paper counts):**

| Pair | Approx. papers |
|---|---|
| Carolin / Maíra | 947 |
| Michael / Maíra | 352 |
| Maíra / Steph | 151 |
| Daniel / Greg | 251 |
| Heidi / Shanon | 246 |
| Steve / Jan | 451 |
| Steph / Batya | 701 |
| Priscilla / Heidi | 200 |
| Priscilla / Sanaz | 399 |
| Shanon / Daniel | 587 |

**Data sources:**

- IEEE Xplore — queried via institutional proxy access.
- ACM Digital Library — additional papers merged via BibTeX.
- Combined into a single merged `.bib` file (~20,000 entries pre-deduplication).
- Final unique corpus: ~10,987 papers after deduplication.

## 2. Spreadsheet structure

The master spreadsheet contains project data across multiple tabs:

| Tab name | Purpose | Approx. rows |
|---|---|---|
| Master paper list | Master paper list with all metadata | ~10,987 |
| Responses | App submissions (Y/N/M answers from the web app) | ~6,000+ |
| Manual Answers | Excel-based answers (2 rows per paper per reviewer) | ~8,572 |
| Consolidated | Merged Responses + Manual Answers (single source of truth) | ~6,910 |
| IN | Papers where both reviewers answered Y (or Y+M) | ~1,007 |
| OUT | Papers where both reviewers answered N (or N+M) | ~6,833 |
| Discussion | Papers where reviewers disagreed (Y+N or M+M) | ~689 |
| Judging | Discussion papers assigned to a third-person judge | ~966 |
| Status | Auto-generated progress reports (append-only history) | ~466 |

**Master sheet column layout** (fixed — automation scripts depend on exact column indices):

| Col | Header | Notes |
|---|---|---|
| A | Key | Unique citation key |
| B | Item Type | Article, conference paper, etc. |
| C | PAIR | Reviewer pair assigned to this paper |
| D | Year | Publication year |
| E | Author | Author(s) |
| F | Title | Paper title |
| G | Publication Title | Journal or conference name |
| H | ISBN | |
| I | ISSN | |
| J | DOI | Digital Object Identifier |
| K | URL | |
| L | Abstract Note | Full abstract |
| M | Date | |
| N | Pages | |
| O–U | Q1–Q7 | 7 screening questions (headers read dynamically from row 1) |
| V | PDF | Drive link to paper PDF |

## 3. Paper screening web app (Google Apps Script)

A Google Apps Script web app replaced Google Forms for screening. It reads live from the spreadsheet and writes responses to a separate `Responses` tab without modifying the original data. Files: `Code.gs` (backend) + `index.html` (frontend). No external dependencies.

### 3.1 `Code.gs` — backend logic

Key constants:

```js
SHEET_NAME = 'ITiCSE2026-WG10-New'
RESPONSES_NAME = 'Responses'
MAYBE_INDICES = [1, 2, 4, 5, 6] // 0-based: Q2, Q3, Q5, Q6, Q7 have a Maybe option
COL.PDF = 22 // Column V (1-based)
```

Key functions:

- `doGet(e)` — serves the web app HTML page.
- `getScreeningData()` — single range read of the entire sheet; returns pairs, members, papers (with metadata + PDF link), Y/N questions, `maybeIndices`, and a reviewed map.
- `buildReviewedMap(ss)` — reads the `Responses` tab and keys the reviewed map as `'pair||reviewer'` (not just `'reviewer'`), so a paper assigned to two pairs with the same title isn't incorrectly marked reviewed in both.
- `submitScreening(payload)` — appends one row to `Responses`; auto-creates the tab with a header if it doesn't exist. Payload: `{pair, reviewer, title, meta, answers, notes}`.
- `clean(val)` — helper that converts `null`/`undefined` to an empty string and trims.

### 3.2 `index.html` — frontend UI

Single-file frontend (HTML + CSS + JS), no external dependencies. Flow (4 steps):

1. **Pair** — dropdown of all reviewer pairs, read live from the sheet.
2. **Reviewer** — shows only the two names in the selected pair.
3. **Paper** — titles for that pair only; already-reviewed titles shown with a checkmark. Pair + reviewer name are remembered in `localStorage` so returning users skip straight to this step.
4. **Screen** (combined) — left panel (58%) shows paper details (title, year, authors, publication, DOI, URL, PDF button, scrollable abstract); right panel (42%) shows the 7 Y/N/M questions and a notes field.

### 3.3 UI features and evolution

- `localStorage` remembers pair + reviewer on first use; the app opens directly at Step 3 on return visits, with a banner showing the current identity and a "Change" link.
- A PDF button appears in Step 4 if a Drive link exists in column V; otherwise a "PDF not available" message is shown.
- Q1 and Q4 are pre-filled as "Y — Yes" for a new paper (default assumptions); the reviewer can change them.
- Only the last question (Q7) is mandatory; Q1–Q6 are optional.
- Answers reset visually when advancing to a new paper.
- Responsive layout: stacks vertically on narrow/mobile screens.

## 4. PDF linking pipeline

> **Redaction note:** the original working document included a live third-party API key for the Zotero library used in this step. That key has been **removed** from this public document. If you re-run this pipeline, generate your own API key from your Zotero account settings and load it from an environment variable or a local, git-ignored config file — never commit it to source control.

Papers were stored locally in a Zotero library, using Zotero's standard key-based storage folder structure. A Python script matched local PDFs to spreadsheet rows and uploaded them to a shared Google Drive folder, writing the resulting share links back to column V of the master sheet. Approximately 6,714 PDFs were matched and uploaded this way.

### 4.1 `zotero_to_drive.py`

Runs locally on the researcher's machine and requires Google OAuth credentials (`credentials.json`, not committed) plus a Zotero API key (supplied via environment variable, not committed).

**Algorithm:**

1. Fetch all items from the Zotero group library via the Zotero API (key + DOI + title).
2. Fetch all PDF attachment items via the API (attachment key → parent item key).
3. For each attachment, look for the corresponding PDF in the local Zotero storage folder.
4. Match spreadsheet rows by DOI first, then by fuzzy title match (88% threshold).
5. Check the Google Drive folder for already-uploaded files to avoid re-uploading.
6. Upload new PDFs to the Drive folder and set sharing permissions to "anyone with the link can view."
7. Write the shareable links to column V using a tab-scoped batch update (not a spreadsheet-level update — see bug note below).
8. Also write links to the "Manual Answers" tab, column W, for both reviewer rows per paper.

**Key bugs fixed during development:**

- *Wrong tab:* an early version used a spreadsheet-level batch update, which defaulted to the first tab. Fixed by scoping the update to the correct worksheet.
- *Re-uploading:* added a check against already-uploaded filenames to skip files on subsequent runs.
- *Column out of bounds:* column V didn't exist yet in some sheets; fixed by adding the column before writing its header.

### 4.2 `fix_manual_answers.py`

A standalone script that writes PDF Drive links to column W of the "Manual Answers" tab, matching by DOI first and then by fuzzy title. Handles both reviewer rows per paper automatically, since they share the same DOI/title. (One issue encountered: the tab name in the spreadsheet didn't exactly match what the script expected — resolved with a small diagnostic helper script that lists all tab names.)

## 5. Apps Script automation functions

Automation functions must be run in this order:

| Order | Function | Purpose |
|---|---|---|
| 1 | `consolidateResponses()` | Merge Responses + Manual Answers → Consolidated |
| 2 | `classifyPapers()` | Assign IN / OUT / Discussion / Waiting based on Q7 |
| 3 | `processJudging()` | Resolve Discussion papers using the judge's decision |
| 4 | `statusReport()` | Build the Status sheet with pair progress and agreement % |
| 5 | `individualReviewerStats()` | Add per-person evaluation counts to the Status sheet |

### 5.1 `consolidateResponses()`

Merges `Responses` (matched by title) and `Manual Answers` (matched by key) into a single `Consolidated` tab. When the same reviewer + title appears in both sources, the `Responses` version is kept (it carries a timestamp). Answers are normalized to Y/N/M, and reviewer name variants (e.g., accented vs. unaccented) are normalized.

### 5.2 `classifyPapers()`

Groups `Consolidated` rows by key. For each key with exactly two reviews, routes the paper based on the Q7 answers:

| Q7 combination | Destination | Rationale |
|---|---|---|
| Y + Y | IN | Both reviewers agree it's relevant |
| Y + M | IN | One certain, one uncertain — include |
| N + N | OUT | Both agree it's not relevant |
| N + M | OUT | One certain out, one uncertain — exclude |
| Y + N | Discussion | Genuine disagreement |
| M + M | Discussion | Both uncertain — needs discussion |
| Only 1 review | Waiting | Second reviewer hasn't submitted yet |

### 5.3 `processJudging()`

Reads the `Judging` sheet, where Discussion papers are assigned to a third-person judge. Routes papers based on the judge's decision: both rows Y → IN; both rows N → OUT; disagreement or blank stays in Discussion. Updates the `Consolidated` status and removes resolved papers from `Discussion`.

### 5.4 `statusReport()`

Builds a timestamped snapshot prepended to the `Status` sheet on each run (history is never overwritten), containing: a pair-completion table, a paper-classification summary (counts and % for IN/OUT/Discussion/Waiting), and an agreement percentage per pair.

### 5.5 `individualReviewerStats()`

Adds a per-person table to the `Status` sheet: papers evaluated, papers judged, papers still waiting on that reviewer, and total contribution.

## 6. Data fixes and corrections

Several data-integrity issues were discovered and corrected during the project, then re-propagated by re-running the automation pipeline:

- **Mislabeled reviewer pair** — a stale `localStorage` value in the web app caused ~51 rows to be logged under a pair that didn't exist in the master sheet, hiding those reviews from the progress report. Fixed by correcting the pair label on the affected rows, and by hardening `buildReviewedMap()` to key on `'pair||reviewer'` instead of `'reviewer'` alone.
- **Missing paper for a reviewer** — the same stale-`localStorage` bug caused one paper to be logged under the wrong pair; complicated by the fact that the same paper title existed under two different keys (a duplicate in the corpus with different citation keys). Fixed by correcting the pair label; this also revealed a genuinely unreviewed duplicate that needed a fresh review.
- **Judging sheet fixes**, applied in three rounds:
  1. *Title/metadata mismatch* — a block of rows had metadata shifted by one row relative to their (correct) key; fixed by treating the key as authoritative and overwriting metadata from the master sheet.
  2. *Duplicate rows* — pattern of duplicate unjudged rows alongside legitimate judged rows; duplicates were deleted, leaving each key with exactly two rows.
  3. *Answer mismatches* — the same row-shift bug affected Q1–Q7 answers for a block of rows; fixed by looking up the correct answers from `Consolidated` using key + reviewer.
  4. *Final verification* — cross-checked against `Responses` and `Manual Answers` directly to confirm the fixes were complete and consistent.

## 7. Key decisions and design principles

- **Never modify the master sheet.** All scripts read from the master list but only ever write to `Responses` or derived tabs.
- **Pair-aware reviewed map.** Keying by `'pair||reviewer'` (not just `'reviewer'`) is critical because duplicate papers in the corpus can be assigned to two different pairs under different keys.
- **`Responses` beats `Manual Answers`** when the same reviewer/paper appears in both, since the `Responses` entry carries a timestamp.
- **`Y+M` → IN, `N+M` → OUT** (changed from an earlier rule that sent any "Maybe" combination to Discussion): a Maybe alongside a Yes reads as "probably include"; a Maybe alongside a No reads as "probably exclude." Genuine disagreement (Y+N) and double uncertainty (M+M) still go to Discussion.
- **The Status sheet is append-only** — each run prepends a new snapshot rather than overwriting history.
- **Key, not Title, is the authoritative identifier** when resolving data mismatches, since titles can be duplicated across distinct papers.
- **Only Q7 is mandatory** for a submission, since it's the field used for classification.
- **Question headers are read dynamically** from row 1 at runtime rather than hardcoded, so the app tolerates wording changes.
- **Deduplication uses article-level identifiers** — a raw result count from a database is not the same as a count of unique documents; the true unique corpus was roughly half of the raw combined total.

## 8. File and script inventory

**Google Apps Script files** (bound to the master spreadsheet):

- `Code.gs` — web app backend (`doGet`, `getScreeningData`, `buildReviewedMap`, `submitScreening`, `clean`)
- `index.html` — web app frontend (HTML/CSS/JS)
- `FetchAbstracts.gs` — fetches full abstracts via an external scholarly API, resumable across runs
- `FindMissingDOIs.gs` — finds DOI + URL for papers missing both, via a chain of external lookups
- `FindIEEE.gs` — targets remaining missing papers using an IEEE-specific lookup
- `consolidateResponses.gs`, `classifyPapers.gs`, `processJudging.gs`, `statusReport.gs`, `individualReviewerStats.gs` — described above
- `fixMislabeledPairs.gs`, `fixMissingMairaPaper.gs` — one-time data fixes described above
- `testWhichSheet.gs` — diagnostic to confirm which spreadsheet a script is bound to

**Python scripts** (run locally by the researcher):

- `zotero_to_drive.py` — matches Zotero PDFs to spreadsheet rows, uploads to Drive, writes links back to the sheet (dependencies: a Zotero API client, a Google Sheets client, the Google API client, and a fuzzy-matching library)
- `fix_manual_answers.py` — writes PDF Drive links to the Manual Answers tab
- `list_tabs.py` — diagnostic script to list all tab names in the spreadsheet

Place the actual script files in [`../../scripts/apps-script/`](../../scripts/apps-script/) and [`../../scripts/python/`](../../scripts/python/) respectively — see the `README.md` in each folder.

---

**A note on credentials:** none of the scripts described above should ever be committed with real API keys, OAuth tokens, or `credentials.json` files. Use environment variables or a local, git-ignored `.env`/`config` file instead (the repository's `.gitignore` already excludes common patterns for this — extend it if you add new credential file names).
