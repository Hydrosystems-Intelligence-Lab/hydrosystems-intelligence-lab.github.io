---
layout: manual
title: Research Workflows
summary: Practical habits for organizing projects, data, analyses, and reproducible outputs.
---

## Project Organization

Each project should have a clear home for code, data notes, documentation, and outputs. Keep raw data separate from processed data and document every step needed to reproduce figures and tables.

Recommended top-level structure:

```text
project-name/
  data/
  docs/
  notebooks/
  outputs/
  scripts/
  src/
  README.md
```

## Reproducibility

- Write a README before the project becomes complicated.
- Track code in Git.
- Record package dependencies in `environment.yml`, `requirements.txt`, or another project-appropriate file.
- Keep raw data unchanged.
- Document data sources, licenses, spatial coverage, temporal coverage, and processing assumptions.
- Save scripts used to generate figures and tables.
- Record random seeds, model versions, configuration files, and compute environment details when they affect results.

## Meetings

For recurring project meetings, keep a lightweight running agenda with:

- Updates since the last meeting
- Decisions needed
- Blockers
- Action items
- Next milestone

## Archiving

Before a paper, report, or dataset is finalized, confirm that the analysis can be rerun from documented inputs and that the final outputs are stored in a stable location.

## Project README Minimum

Every active project should eventually include:

- Research question
- Repository owner or point of contact
- Data sources and access notes
- Environment setup
- Reproduction steps
- Output locations
- Known limitations
