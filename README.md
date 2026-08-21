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

**Methodology.** The investigation employs a multi-phase approach: a systematic literature review (SLR) of teamwork in computing and engineering education contexts, a qualitative investigation of educator viewpoints, identification of best practices and gaps, and participatory co-design of instructional resources with faculty and students.

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

## Repository structure

```
ITiCSE2026_Teamwork_Skills-Values-Virtues/
├── README.md                        This file
├── LICENSE                          Usage terms (CC BY-NC 4.0)
├── CITATION.cff                     How to cite this repository
├── .zenodo.json                     Metadata used by Zenodo when archiving a GitHub release
├── docs/                            Project overview, methodology write-ups, and appendices (spans all phases)
│   ├── project-overview.md            Full WG10 proposal text (purpose, motivation, methodology, expectations)
│   ├── methodology/                    How the SLR and its AI-assisted extraction were designed and run
│   └── appendices/                     Supplementary appendices referenced in the SLR write-up
├── figures/                         Diagrams and screenshots referenced from docs/
├── systematic-literature-review/    Phase 1 — SLR: screening and extraction tables, plus the tooling behind them
│   ├── data/                           Screening (Phase 1) and extraction (Phase 2) tables
│   └── scripts/                        Apps Script + Python tooling behind the screening pipeline
├── focus-group/                     Focus-group protocol, sessions, and analysis — placeholder
├── survey/                          Survey instrument, data, and analysis — placeholder
└── community-collaboration/         Participatory co-design resources and working-session notes — placeholder
```

## What's in each folder

**[`docs/`](./docs/)** — Start here. The full WG10 project overview, plus the methodology write-ups and appendices for the systematic literature review (how papers were screened and how data was extracted, including the AI-assisted extraction prompts). As the other strands below produce their own write-ups, those can live here too, alongside the SLR ones.

**[`figures/`](./figures/)** — Diagrams and screenshots referenced from `docs/` (for example, the screening-tool screenshots referenced in the appendices).

**[`systematic-literature-review/`](./systematic-literature-review/)** — Phase 1 of the methodology above. This is the strand that's populated so far: the resulting screening and data-extraction tables, and the tooling used to produce them (a paper-screening web app and supporting scripts). The write-up describing this process lives in `docs/methodology/`, not here.

**[`focus-group/`](./focus-group/)** — *Placeholder, not yet populated.* Will hold the focus-group protocol, session materials, and thematic analysis from the qualitative educator-perspectives phase of the methodology (objective 2 above).

**[`survey/`](./survey/)** — *Placeholder, not yet populated.* Will hold the survey instrument, de-identified response data, and analysis, from the same qualitative educator-perspectives phase.

**[`community-collaboration/`](./community-collaboration/)** — *Placeholder, not yet populated.* Will hold the resources, working-session notes, and community feedback from the participatory co-design phase (objective 4 above).

Each folder — including the three placeholders — has its own `README.md` with more detail on the suggested contents and any data-handling notes (for example, de-identifying participant data from focus groups and surveys before it's committed).

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
