---
layout: manual
title: Group Software
summary: A place to document software developed or maintained by the Abeshu Hydrosystems Intelligence Group.
---

## Purpose

This page defines the working standards for group-developed software, model workflows, packages, and reusable scripts. Public-facing software and datasets are summarized on the [Software & Data]({{ '/software-data/' | relative_url }}) page.

Each software entry should include:

- Repository link
- Purpose
- Installation instructions
- Minimal example
- Input data requirements
- Output description
- Citation or acknowledgement guidance
- Maintainer

## Repository Standards

For public or shared repositories, include:

- `README.md`
- License when appropriate
- Environment or dependency file
- Example data or a small test case when possible
- Clear instructions for reproducing main outputs
- Citation information when the tool supports a publication

## Candidate Categories

- Hydrologic modeling workflows
- Earth observation processing
- Lake and reservoir analytics
- Infrastructure operations and decision support
- Equity and community water analysis
- Figure-generation tools

## Model Workflows

When developing or adapting hydrologic, Earth system, or machine learning models, adhere to the following workflow standards to ensure reproducibility and usability across the group:

- **Configuration Management**: Do not hardcode file paths, local directories, or core model parameters in the source code. Use version-controlled configuration files (e.g., `.yaml`, `.json`, or `.ini`).
- **Environment Specification**: Always include an `environment.yml` (for Conda/Mamba) or `requirements.txt` (for pip) pinned to the exact package versions used during model development.
- **Data Separation**: Model code must remain separate from large input and output datasets. Scripts should read data from approved shared storage (e.g., HPC Project Space or Group NAS) using configurable paths.
- **Minimal Test Case**: Provide a small, fast-running test case (a "dummy" or "toy" dataset) that allows a new user to verify the model runs correctly without needing to download terabytes of data or wait hours for a run to finish.
- **Reproducibility Logs**: Where possible, design the model workflow to automatically log its execution environment, random seeds, hyperparameters, and the exact configuration used alongside the output files.
- **Containerization**: For highly complex or computationally heavy models deployed on NMSU HPC or external clusters, consider using Apptainer/Singularity or Docker to package the exact OS and dependency stack.
