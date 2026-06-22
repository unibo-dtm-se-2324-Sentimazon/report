---
title: CI/CD
has_children: false
nav_order: 9
---

# CI/CD

Continuous Integration and Continuous Deployment are important DevOps practices used to automate validation, testing, and publication of software. Continuous Integration means integrating code changes frequently and checking that the project still works after each change. This helps detect problems earlier instead of finding them only at the end of development.

In the Sentimazon project, the CI/CD approach is mainly focused on project reproducibility, automated testing, and report deployment. The project is developed as a Python-based sentiment analysis tool using a Jupyter Notebook and reusable Python modules. Therefore, the most relevant automation tasks are setting up the Python environment, running automated tests, and keeping the online report updated.

## Continuous Integration

A Continuous Integration workflow was implemented using GitHub Actions. The workflow is stored in:

```text
.github/workflows/ci.yml
```

GitHub Actions does not automatically create the workflow file by itself. The workflow file must be added to the repository. After the file was created and pushed to GitHub, GitHub Actions automatically detected it and executed the workflow.

The workflow follows the basic GitHub Actions structure taught in class: a workflow is triggered by events, the workflow contains jobs, and each job contains ordered steps. The workflow runs on a fresh virtual machine, called a runner, using `ubuntu-latest`.

The CI workflow is triggered by:

- Push events
- Pull request events
- Manual execution through `workflow_dispatch`

The revised CI workflow performs the following automated steps:

1. Checks out the repository
2. Sets up Python
3. Installs the required test dependencies
4. Runs the automated test suite using `pytest`

The current workflow is:

```yaml
name: CI

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: "3.10"

      - name: Install test dependencies
        run: |
          python -m pip install --upgrade pip
          pip install pandas scikit-learn nltk pytest

      - name: Run automated tests
        run: |
          PYTHONPATH=src pytest
```

The first version of the CI workflow only checked whether some files existed, such as the notebook and the requirements file. This was limited because it did not verify whether the project logic actually worked.

After the revision, the CI workflow was improved to run automated tests. This means that GitHub Actions now validates the main project modules instead of only checking file existence.

The current automated test suite checks:

- Data loading
- Text preprocessing
- Aspect extraction
- Evaluation metrics

The CI run was completed successfully, confirming that the test suite can run in a clean GitHub Actions environment.

## Continuous Deployment

The Continuous Deployment part of the project is mainly related to the publication of the project report. The report is deployed using GitHub Pages, which makes the documentation available online.

This deployment process is useful because it keeps the online report synchronized with the repository. When the report files are updated and pushed to GitHub, GitHub Pages can publish the updated version of the report. This reduces manual work and makes the project easier to present and review.

The report repository contains the documentation structure, including files such as:

```text
index.md
_config.yml
sections/
```

These files are used to organize and build the online report.

The project itself is not deployed as a web application. Instead, it is released and shared through the GitHub repository and GitHub Releases. The stable revised version was published as:

```text
v1.0.0 - Sentimazon Refactored Version
```

## GitHub Actions, Secrets, and Environment Variables

GitHub Actions workflows are configured using YAML files stored in the `.github/workflows/` folder. In GitHub Actions, `run` is used to execute shell commands, while `uses` is used to call reusable GitHub Actions such as `actions/checkout` or `actions/setup-python`.

At the current stage, the Sentimazon project does not require complex secrets or private environment variables. It does not use a private API, database, or protected production server. Since the Amazon scraping component was postponed, no Amazon-related API key or scraping credential is required.

If future versions of the project include real-time scraping, external APIs, private datasets, or automatic deployment requiring credentials, sensitive values should not be written directly in the code or in the workflow file. Instead, they should be stored as GitHub repository secrets and accessed inside the workflow through the `secrets` context. This prevents private data from being exposed in the repository.

## Future Improvements

The current CI workflow validates the main lightweight parts of the project using automated tests. Future improvements could include:

- Automated notebook execution
- More unit tests for additional functions
- Linting and formatting checks
- Testing on multiple Python versions
- Testing on multiple operating systems
- Optional test jobs for transformer-based models

A build matrix could also be added to test the project on different Python versions or operating systems. This would improve portability and make the workflow closer to a complete CI pipeline.

Overall, the Sentimazon project now includes a working CI workflow using GitHub Actions and uses GitHub Pages for report deployment. This improves the reproducibility and maintainability of the project and provides a foundation for more advanced automation in the future.