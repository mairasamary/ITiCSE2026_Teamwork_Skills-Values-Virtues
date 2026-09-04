# Systematic Literature Review

The final list of papers in our SLR contains 555 papers. The full reference list is in [`SLR-PrimaryStudliesReferences.pdf`](./SLR-PrimaryStudliesReferences.pdf), and the same list as a title/authors/year/venue table is in [`SLR-PrimaryStudliesTable.pdf`](./SLR-PrimaryStudliesTable.pdf) — also available in a more browsable form as [`primary-studies.md`](./primary-studies.md) (or [`primary-studies.csv`](./primary-studies.csv)):

| # | Title | Authors | Year | Venue |
|---|---|---|---|---|
| 1 | A method to analyze computer science students' teamwork in online collaborative learning environments | Rebecca Vivian, Katrina Falkner, Nickolas Falkner et al. | 2016 | ACM Transactions on Computing Education |
| 2 | Academy-industry collaboration and the effects of the involvement of undergraduate students in real world activities | Elaine Venson, Rejane Figueiredo, Wander Silva et al. | 2016 | 2016 IEEE Frontiers in Education Conference (FIE) |
| 3 | Applying scrum project management in ECE curriculum | Robert B. Bass, Branimir Pejcinovic, John Grant | 2016 | 2016 IEEE Frontiers in Education Conference (FIE) |
| … | *(549 more rows)* | | | |

See [`primary-studies.md`](./primary-studies.md) for the complete list. **Note:** that extraction currently has 552 rows, not 555 — see the note at the top of that file.

- [`screening-tool-documentation.md`](./data/screening/screening-tool-documentation.md) — how the two-reviewer screening tool and its automation pipeline worked, including the Phase 1 title/abstract screening process, the master spreadsheet structure, and the data fixes applied along the way.
- [`data/`](./data/) — the screening/eligibility decision tables (Phase 1 title/abstract, Phase 2 full-text, plus forward/backward snowballing) and the SLR flow diagram explaining how they connect (see [`data/screening/README.md`](./data/screening/README.md)); `data/extraction/` documents an AI-assisted extraction approach that was explored but not used in the study.
- [`scripts/`](./scripts/) — the Apps Script and Python tooling behind the screening pipeline.

For the AI-assisted data-extraction methodology, see [`data/extraction/ai-assisted-extraction.md`](./data/extraction/ai-assisted-extraction.md).
