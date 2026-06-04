---
title: CI/CD
has_children: false
nav_order: 9
---

# CI/CD

Continuous Integration and Continuous Deployment are important DevOps practices used to automate the validation, building, testing, and publication of software. Continuous Integration means integrating code frequently with the main development line and verifying that the project still works after each change. This helps avoid integration problems being discovered too late in the development process.

In the Sentimazon project, the CI/CD approach is mainly focused on project reproducibility, basic automated validation, and report deployment. The project is developed as a Python-based sentiment analysis tool using a Jupyter Notebook. Therefore, the most relevant automation tasks are setting up the Python environment, installing dependencies, validating the presence of the main project files, and keeping the online report updated.

## Continuous Integration

A basic Continuous Integration workflow has been implemented using GitHub Actions. The workflow is stored in:

.github/workflows/ci.yml

GitHub does not automatically create the workflow file by itself. Instead, the workflow file must be added to the repository. After the file was created and pushed to GitHub, GitHub Actions automatically detected it and executed the workflow on the next push to the main branch.

The workflow follows the basic GitHub Actions structure taught in class: a workflow is triggered by events, the workflow contains jobs, and each job contains ordered steps. The workflow runs on a fresh virtual machine, called a runner, using ubuntu-latest.

The CI workflow is triggered by:

push to main
pull request to main
manual workflow_dispatch

The implemented workflow performs the following automated steps:

1. Checkout repository
2. Set up Python 3.10
3. Install dependencies from requirements.txt
4. Validate the presence of Main.ipynb and requirements.txt

The workflow uses actions/checkout@v4 to clone the repository inside the GitHub Actions runner. This is necessary because GitHub Actions runners do not automatically clone the repository unless the checkout action is used. Then, actions/setup-python@v5 is used to install Python 3.10. After that, the dependencies are installed from requirements.txt. Finally, the workflow checks that the main project files, Main.ipynb and requirements.txt, exist in the repository.

The implemented workflow is:

name: CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]
  workflow_dispatch:

jobs:
  validate:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: "3.10"

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt

      - name: Validate project files
        run: |
          test -f Main.ipynb
          test -f requirements.txt

The first CI run was completed successfully. This confirms that GitHub Actions was able to check out the repository, set up Python, install dependencies, and validate the project files.

This CI workflow is useful because it provides an automated and reproducible validation process. Instead of relying only on manual checks, GitHub Actions runs the same validation steps in a clean environment. This helps detect dependency or project-structure problems earlier.

The project was originally planned to perform real-time sentiment analysis using Amazon review scraping. However, due to Amazon policy limitations and scraping restrictions, the scraping component was postponed. Instead, a Kaggle dataset was used. This choice makes the project more reproducible because the analysis does not depend on unstable external scraping access.

The main analysis pipeline includes loading the dataset, cleaning review texts, removing stop words, tokenization, lemmatization, part-of-speech tagging, aspect extraction, and sentiment analysis. Product aspects such as battery, price, quality, and performance are extracted from the reviews. Then, different sentiment analysis models, including VADER, DistilBERT, and RoBERTa, are applied and compared using accuracy, precision, recall, and F1-score.

## Continuous Deployment

The Continuous Deployment part of the project is mainly related to the publication of the project report. The report repository is deployed using GitHub Pages, which makes the documentation available online.

This deployment process is useful because it keeps the online report synchronized with the repository. When the report files are updated and pushed to GitHub, GitHub Pages can publish the updated version of the report. This reduces manual work and makes the project easier to present and review.

The report repository contains the documentation structure, including the sections/ folder, _config.yml, and index.md. These files are used to organize and build the online report.

## GitHub Actions, Secrets, and Environment Variables

GitHub Actions workflows are configured using YAML files stored in the .github/workflows/ folder. In GitHub Actions, run is used to execute shell commands, while uses is used to call reusable GitHub Actions such as actions/checkout or actions/setup-python.

At the current stage, the Sentimazon project does not require complex secrets or private environment variables. It does not use a private API, database, or protected production server. Since the Amazon scraping component was postponed, no Amazon-related API key or scraping credential is required.

If future versions of the project include real-time scraping, external APIs, private datasets, or automatic deployment requiring credentials, sensitive values should not be written directly in the code or in the workflow file. Instead, they should be stored as GitHub repository secrets and accessed inside the workflow through the secrets context. This prevents private data from being exposed in the repository.

## Future Improvements

The current CI workflow is intentionally simple. It validates the basic project structure and dependency installation, but it does not yet execute the full notebook or run automated unit tests.

Future improvements could include automated notebook execution, simple test scripts for preprocessing and sentiment-analysis functions, linting, formatting checks, and a build matrix for multiple Python versions. A build matrix could test the project on different Python versions or operating systems, improving portability and making the workflow closer to a complete CI pipeline.

Overall, the Sentimazon project now includes a basic working CI workflow using GitHub Actions and uses GitHub Pages for report deployment. This improves the reproducibility and maintainability of the project and provides a foundation for more advanced automation in the future.