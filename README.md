# ITiCSE 2026 WG10 — Teamwork in Computing Education: Skills, Values, and Virtues

This repository contains the materials, data, and tools produced by **ITiCSE 2026 Working Group 10 (WG10)**, convened as part of the [27th Annual Conference on Innovation and Technology in Computer Science Education (ITiCSE 2026)](https://iticse.acm.org/2026/), taking place in Madrid, Spain.

- **Working group proposal:** https://iticse.acm.org/2026/2026-working-group-proposals/
- **Organizers:** Stephanie Lunn (Florida International University, sjlunn@fiu.edu) and Maíra Marques Samary (Boston College, marquemo@bc.edu)

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

## Repository structure

```
ITiCSE2026_Teamwork_Skills-Values-Virtues/
├── README.md                  This file
├── LICENSE                    Usage terms (CC BY-NC 4.0)
├── CITATION.cff                How to cite this repository
├── .zenodo.json                 Metadata used by Zenodo when archiving a GitHub release
├── docs/
│   ├── project-overview.md      Full WG10 proposal text (purpose, motivation, methodology, expectations)
│   ├── methodology/              How the systematic literature review and AI-assisted extraction were designed and run
│   └── appendices/               Supplementary appendices referenced in the SLR write-up
├── data/
│   ├── extraction/               Phase 2 data-extraction tables (one row per included paper)
│   └── screening/                Phase 1 screening outputs (IN / OUT / Discussion tables)
├── scripts/
│   ├── apps-script/              Google Apps Script tooling used to run the screening web app
│   └── python/                    Python scripts used for PDF linking and data cleanup
└── figures/                      Diagrams and screenshots referenced from the docs
```

See the `README.md` inside `data/`, `scripts/`, and `figures/` for notes on what belongs in each of those folders and how large files are handled.

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
