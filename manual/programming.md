---
layout: manual
title: General Programming
summary: Guidance for coding, computing environments, version control, and collaborative software work.
---

## Environments

Use a dedicated environment for each project. For Python projects, `conda`, `mamba`, or `venv` are all acceptable when the dependency file is documented and committed.

Example:

```bash
conda create -n project-name python=3.11
conda activate project-name
```

## Git Habits

- Commit focused changes with clear messages.
- Avoid committing large raw datasets unless the repository is designed for that purpose.
- Keep generated outputs out of version control unless they are small, stable, and intentionally published.
- Use branches for larger changes.
- Write pull request descriptions that explain what changed and how it was checked.

## Code Style

Prefer readable, boring code over clever code. Use descriptive names, small functions, and clear input/output boundaries.

Add comments only where they explain non-obvious decisions, assumptions, or scientific reasoning.

## Notebooks

Notebooks are useful for exploration and communication. For production analyses, move reusable logic into scripts or package code so figures and tables can be regenerated consistently.

## Large Data

Do not commit large datasets to normal Git repositories. Instead, use one of our approved shared storage locations:

- **Lab NAS**: For primary active research data, large remote-sensing datasets, and model outputs.
- **NMSU OneDrive**: For documents, meeting notes, presentations, and small tabular data.
- **HPC Project Space**: For temporary large-scale model runs and intermediate processing outputs.

When working with large hydrologic or remote-sensing data, document:

- Source URL or provider
- Download date
- Spatial and temporal coverage
- Processing scripts
- Units and coordinate reference system
- Missing data conventions
