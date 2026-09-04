# ITiCSE 2026 WG10 — Teamwork in Computing Education: Skills, Values, and Virtues

This repository contains the materials, data, and tools produced by **ITiCSE 2026 Working Group 10 (WG10)**, convened as part of the [27th Annual Conference on Innovation and Technology in Computer Science Education (ITiCSE 2026)](https://iticse.acm.org/2026/), taking place in Madrid, Spain.

- **Working group proposal:** https://iticse.acm.org/2026/2026-working-group-proposals/
- **Working Group Co-Leaders:** Stephanie J. Lunn, Maíra Marques Samary, and Stephen Frezza — see [Working Group Members](#working-group-members) below for the full team.

## Purpose

This working group examines how tertiary computing programs can effectively integrate teamwork instruction, focusing on the competencies and character attributes students need throughout collaborative projects.

**Motivation.** Teamwork is critical to computing education and for graduates' thriving in the workplace, but it often requires structured support, assessment mechanisms, and feedback systems to succeed.

**Primary objectives.** The group aims to:

1. Identify how the scholarly literature describes integrating skills, values, and virtues (SVV) in computing teams.
2. Explore educator perspectives on fostering these attributes.
3. Assess community successes and priorities.
4. Develop actionable resources for computing courses.

**Research questions:**

- **RQ1.** How do computing and engineering faculty and researchers define teamwork?
- **RQ2.** How do computing and engineering faculty and researchers distinguish successful teamwork?
- **RQ3.** Which skills, values, and virtues (SVV) do computing and engineering faculty describe as aligning with or supporting teamwork in education?

**Methodology.** The investigation employs a multi-phase approach: a systematic literature review (SLR) of teamwork in computing and engineering education contexts, a qualitative investigation of educator viewpoints, identification of best practices and gaps, and participatory co-design of instructional resources with faculty and students. See [`systematic-literature-review/data/extraction/ai-assisted-extraction.md`](./systematic-literature-review/data/extraction/ai-assisted-extraction.md) and [`systematic-literature-review/data/screening/screening-tool-documentation.md`](./systematic-literature-review/data/screening/screening-tool-documentation.md) for how the literature-review phase (screening and data extraction) was actually carried out.

**Working group expectations.** Members commit approximately 3–4 hours weekly for four months pre- and post-conference, participate in biweekly virtual meetings and weekly subgroup sessions, and attend the in-person intensive working sessions at ITiCSE 2026 in Madrid.

**Desired participants.** The group welcomes international educators with experience in team project instruction, particularly early-career researchers and first-time participants willing to recruit colleagues for research participation.

## Working Group Members

### Working Group Co-Leaders

| Name | Affiliation | ORCID | Email |
|---|---|---|---|
| **Stephanie J. Lunn** | Florida International University — Miami, Florida, USA | [0000-0003-3840-1822](https://orcid.org/0000-0003-3840-1822) | sjlunn@fiu.edu |
| **Maíra Marques Samary** | Boston College — Chestnut Hill, Massachusetts, USA | [0000-0001-5347-1664](https://orcid.org/0000-0001-5347-1664) | marquemo@bc.edu |
| **Stephen Frezza** | Franciscan University of Steubenville — Steubenville, Ohio, USA | [0000-0002-5246-3061](https://orcid.org/0000-0002-5246-3061) | sfrezza@franciscan.edu |

### Contributors

| Name | Affiliation | ORCID | Email |
|---|---|---|---|
| Priscilla Jimenez-Pazmino | University of St. Thomas — Saint Paul, Minnesota, USA | [0000-0002-3605-3011](https://orcid.org/0000-0002-3605-3011) | priscilla.jimenez@stthomas.edu |
| Janice L. Pearce | Berea College — Berea, Kentucky, USA | [0000-0001-7566-9217](https://orcid.org/0000-0001-7566-9217) | jan_pearce@berea.edu |
| Daniel Prol | University of Houston — Houston, Texas, USA | [0009-0006-6522-4322](https://orcid.org/0009-0006-6522-4322) | dprol@uh.edu |
| Shanon Reckinger | University of Illinois Chicago — Chicago, Illinois, USA | [0000-0003-1609-9861](https://orcid.org/0000-0003-1609-9861) | shanon@uic.edu |
| Michael James Scott | Falmouth University — Penryn, Cornwall, UK | [0000-0002-6803-1490](https://orcid.org/0000-0002-6803-1490) | michael.scott@falmouth.ac.uk |
| Carolin Wortmann | University of Münster — Münster, Germany | [0009-0006-6956-3372](https://orcid.org/0009-0006-6956-3372) | carolin.wortmann@uni-muenster.de |
| Batya Zamansky | University of Illinois Urbana-Champaign — Urbana, Illinois, USA | [0009-0002-4519-9175](https://orcid.org/0009-0002-4519-9175) | batyaz2@illinois.edu |

### Acknowledgments

This work would not have been possible without the dedicated support of several non-author volunteers, in particular **Heidi Ellis** (heidi.ellis@wne.edu), **Gregory Hislop** (hislop@drexel.edu), and **Sanaz Nikfalazar** (sanaz.nikfalazar1@monash.edu), who were extremely supportive and made significant contributions to the data analysis.

## Repository structure

```
ITiCSE2026_Teamwork_Skills-Values-Virtues/
├── README.md                        This file
├── LICENSE                          Usage terms (CC BY-NC 4.0)
├── CITATION.cff                     How to cite this repository
├── .zenodo.json                     Metadata used by Zenodo when archiving a GitHub release
├── systematic-literature-review/    Phase 1 — SLR: screening/extraction tables, tooling, appendices, figures, and the screening write-up
│   ├── data/                           Screening (Phase 1, 2, snowballing) tables + screening-tool-documentation.md — extraction/ holds the AI-assisted extraction methodology + source materials (extraction table itself pending)
│   ├── appendices/                     Supplementary appendices referenced in the SLR write-up
│   ├── figures/                        Diagrams and screenshots referenced from the appendices and the SLR data
│   └── scripts/                        Apps Script + Python tooling behind the screening pipeline
├── focus-group/                     Focus-group protocol (script + preparation prompts) — sessions and analysis still placeholders
├── survey/                          Survey instrument (pre-survey) — data and analysis still placeholders
└── community-collaboration/         OER materials shared by community collaborators — working-session notes and feedback still placeholders
```

## What's in each folder

**[`systematic-literature-review/`](./systematic-literature-review/)** — Phase 1 of the methodology above. This is the strand that's populated so far: [`data/screening/screening-tool-documentation.md`](./systematic-literature-review/data/screening/screening-tool-documentation.md) explains how the two-reviewer screening tool and its automation pipeline worked (including the Phase 1 title/abstract screening process), alongside the resulting screening tables and the tooling used to produce them (a paper-screening web app and supporting scripts). [`data/extraction/`](./systematic-literature-review/data/extraction/) holds the write-up and source materials from an AI-assisted extraction approach that was explored but not used in the study. [`appendices/`](./systematic-literature-review/appendices/) holds supplementary appendices referenced from the SLR write-up, and [`figures/`](./systematic-literature-review/figures/) holds the diagrams and screenshots referenced from those appendices and from the SLR data (for example, the PRISMA flow diagram).

**[`focus-group/`](./focus-group/)** — Part of the qualitative educator-perspectives phase of the methodology (objective 2 above). [`protocol/`](./focus-group/protocol/) holds the approved moderator script and the participant preparation prompts (including the study's working definitions of skills, values, and virtues). Session materials and thematic analysis are still placeholders.

**[`survey/`](./survey/)** — Part of the same qualitative educator-perspectives phase. [`instrument/`](./survey/instrument/) holds the pre-survey sent to computing educators (academic and industry teamwork background, open-ended questions, demographics, and the focus-group invitation). De-identified response data and analysis are still placeholders.

**[`community-collaboration/`](./community-collaboration/)** — Part of the participatory co-design phase (objective 4 above). [`oer-materials/`](./community-collaboration/oer-materials/) holds open educational resources shared by community collaborators, with a table of contributors, material types, links, and licenses in the folder's [README](./community-collaboration/README.md). Working-session notes and community feedback are still placeholders.

Each folder has its own `README.md` with more detail on its contents (or suggested contents, for the parts still placeholders) and any data-handling notes (for example, de-identifying participant data from focus groups and surveys before it's committed).

## Data and large files

The literature corpus for this SLR is large (~11,000 papers before screening; ~1,000 included after screening), so **the paper PDFs themselves are not stored in this GitHub repository.** Large source materials and full data exports are archived on **Zenodo** (DOI to be added once the first release is published — see below), and only the tables, scripts, and documentation needed to reproduce the process are versioned here in GitHub.

## GitHub + Zenodo archiving

This repository is connected to Zenodo. Tagging a GitHub **release** creates a permanent, citable snapshot of the repository at that point in time and mints a DOI for it automatically. Please cite the **Concept DOI** (which always resolves to the latest version) in papers describing this work, and cite a specific **version DOI** when precise reproducibility of a given snapshot matters.

- Concept DOI: `TBD — add after first Zenodo release`
- Latest version DOI: `TBD — add after first Zenodo release`

## License

This work is licensed under a [Creative Commons Attribution-NonCommercial 4.0 International License](https://creativecommons.org/licenses/by-nc/4.0/) — see [`LICENSE`](./LICENSE) for details. In short: reuse and adaptation are welcome with attribution, but commercial use is not permitted without the authors' permission.

## Citation

If you use these materials, please cite this repository using the information in [`CITATION.cff`](./CITATION.cff).

## Contact

Questions about this working group can be directed to the organizers listed above.
