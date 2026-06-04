---
title: Developer guide
has_children: false
nav_order: 11
---

# Developer Guide

This section is intended for developers who wish to contribute to the Sentimazon project or run it locally for development.

## Repository

The project repository is available at:

```text
https://github.com/unibo-dtm-se-2324-Sentimazon/Sentimazon-Project
```

The project report is available at:

```text
https://unibo-dtm-se-2324-sentimazon.github.io/report/
```

## Issue Reporting

Issues should be reported directly on GitHub.

When reporting a bug, developers should use a clear and descriptive title, for example:

```text
Fix: notebook fails during dataset loading
Fix: missing dependency in requirements.txt
Fix: sentiment model does not run correctly
```

A bug report should include:

```text
Description of the problem
Steps to reproduce the issue
Expected result
Actual result
Screenshot or error message, if available
Operating system
Python version
Branch name
```

Example bug report:

```text
Title: Fix: notebook fails during dataset loading

Description:
The notebook stops when trying to load the dataset.

Steps to reproduce:
1. Clone the repository
2. Install dependencies using pip install -r requirements.txt
3. Open Main.ipynb
4. Run the data loading cell

Expected behavior:
The dataset should load correctly.

Actual behavior:
The notebook returns a file path error.

Environment:
OS:
Python version:
Branch:
```

Feature requests should also be opened as GitHub Issues. A feature request should explain the problem, the proposed solution, and the expected benefit.

Example feature request:

```text
Title: Feature: add automated notebook execution in CI

Problem:
The current CI workflow installs dependencies and validates project files, but it does not execute the notebook.

Proposed solution:
Add a CI step that runs the notebook automatically.

Expected benefit:
Runtime errors can be detected earlier.
```

## Team Communication

Project communication should mainly happen through GitHub Issues and Pull Requests.

Recommended communication channels:

```text
GitHub Issues: bug reports and feature requests
GitHub Pull Requests: code review and implementation discussion
GitHub commit history: tracking project changes
```

Developers should use clear messages when discussing bugs, changes, or new features. If screenshots are shared, they should not contain sensitive information such as private file paths, passwords, tokens, or API keys.

## Branch Naming

The project should follow a simple branch naming convention.

Features:

```text
feature/add-new-model
feature/improve-preprocessing
feature/add-visualization
```

Fixes:

```text
fix/dataset-path-error
fix/missing-dependency
fix/notebook-runtime-error
```

Documentation:

```text
docs/update-user-guide
docs/update-developer-guide
docs/update-cicd-section
```

CI/CD changes:

```text
ci/add-github-actions-workflow
ci/update-validation-step
```

## Code Style

The project follows standard Python coding conventions.

Python code should follow PEP 8 guidelines. Function names and variable names should be written in `snake_case`.

Examples:

```python
def clean_comments(comment):
    ...

cleaned_reviews = []
tokenized_comments = []
lemmatized_comments = []
```

Constants should be written in uppercase:

```python
RELEVANT_ASPECTS = ["battery", "price", "quality", "performance"]
```

Developers should follow these rules:

```text
Use clear and descriptive variable names
Avoid unnecessary duplicated code
Avoid unused imports
Avoid hardcoded local file paths
Avoid committing private files or credentials
Keep notebook cells readable and organized
Use Markdown cells to explain important steps
```

Imports should be grouped logically:

```text
Standard library imports
Third-party library imports
Project-specific code, if added in the future
```

## File Organization

The repository has a simple notebook-based structure.

```text
Sentimazon-Project/
├── .github/
│   └── workflows/
│       └── ci.yml              # GitHub Actions CI workflow
├── Main.ipynb                  # Main sentiment analysis notebook
├── requirements.txt            # Python dependencies
└── README.md                   # General project information
```

The main analysis is implemented in:

```text
Main.ipynb
```

The dependency list is stored in:

```text
requirements.txt
```

The CI workflow is stored in:

```text
.github/workflows/ci.yml
```

Developers should avoid placing temporary files, private datasets, local environment folders, or large generated outputs in the repository.

Ignored or non-committed files should include:

```text
venv/
.venv/
__pycache__/
.ipynb_checkpoints/
.env
Local datasets, if too large or private
Private API keys or credentials
```

## Pull Request Process

Developers should create a Pull Request when they want to merge changes into the main branch.

A Pull Request should include:

```text
What problem does the change solve?
What functionality does it add or modify?
Which files were changed?
How was the change tested?
Are there any limitations?
```

Example Pull Request description:

```text
Summary:
Updated the preprocessing section of the notebook.

Reason:
The previous text cleaning step was not clearly separated from stop-word removal.

Testing:
The notebook was run from the dataset loading step to the model evaluation step.

Limitations:
No automated unit tests were added.
```

Before opening a Pull Request, developers should:

```text
Run the notebook locally
Check that dependencies install correctly
Check that the dataset path is reproducible
Make sure no private files are committed
Write a clear commit message
```

Merging should only happen after the changes are reviewed and the CI workflow passes.

## Project Structure

The project is organized as a simple Python/Jupyter Notebook repository.

```text
Sentimazon-Project/
├── .github/
│   └── workflows/
│       └── ci.yml
├── Main.ipynb
├── requirements.txt
└── README.md
```

The project does not have a backend/frontend architecture. It is not a deployed web application. Instead, it is a notebook-based sentiment analysis pipeline.

The main notebook performs the following operations:

```text
Load the review dataset
Select review text and sentiment columns
Clean the review text
Remove stop words
Tokenize comments
Lemmatize words
Apply part-of-speech tagging
Extract product aspects
Run sentiment analysis models
Compare model performance
```

The main sentiment analysis models used are:

```text
VADER
DistilBERT
RoBERTa
```

The evaluation metrics used are:

```text
Accuracy
Precision
Recall
F1-score
```

## Development Setup

## Prerequisites

Before contributing, developers should install:

```text
Python 3.10 or higher
Git
pip
Visual Studio Code, Jupyter Notebook, or JupyterLab
A GitHub account
```

Recommended VS Code extensions:

```text
Python
Jupyter
Pylance
GitLens
```

## Installation

## Clone the Repository

```bash
git clone https://github.com/unibo-dtm-se-2324-Sentimazon/Sentimazon-Project.git
```

Move into the project folder:

```bash
cd Sentimazon-Project
```

## Create a Virtual Environment

```bash
python -m venv venv
```

## Activate the Virtual Environment

On Windows:

```bash
venv\Scripts\activate
```

On Linux or macOS:

```bash
source venv/bin/activate
```

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Running the Project

Open the main notebook:

```text
Main.ipynb
```

The notebook can be opened using:

```text
Visual Studio Code
Jupyter Notebook
JupyterLab
```

Then run the cells from top to bottom.

Developers should run the notebook sequentially because later cells depend on variables created in earlier cells.

## Dataset Configuration

The project uses a mobile review sentiment dataset. Before running the notebook, make sure the dataset file is available locally.

The project was originally planned to perform real-time sentiment analysis on Amazon reviews using an Amazon review scraper. However, due to Amazon policy limitations and scraping restrictions, the scraping component was postponed. Therefore, the project currently uses a static Kaggle dataset to make the analysis more stable and reproducible.

The notebook should use a reproducible file path. Developers should avoid absolute local paths such as:

```python
data = pd.read_csv("E:\\Class\\software\\Mobile_Reviews_Sentiment.csv")
```

Instead, use a relative path, for example:

```python
data = pd.read_csv("Mobile_Reviews_Sentiment.csv")
```

or:

```python
data = pd.read_csv("data/Mobile_Reviews_Sentiment.csv")
```

This makes the project easier to run on other computers.

## Notebook Pipeline

The main project pipeline is implemented in `Main.ipynb`.

The notebook includes:

```text
Dataset loading
Text cleaning
Stop-word removal
Tokenization
Lemmatization
Part-of-speech tagging
Noun and aspect extraction
VADER sentiment analysis
DistilBERT sentiment analysis
RoBERTa sentiment analysis
Model evaluation
```

The relevant product aspects include:

```text
battery
price
quality
performance
```

The output of the notebook includes:

```text
Cleaned review data
Tokenized comments
Lemmatized comments
Extracted aspects
Sentiment labels from VADER
Sentiment labels from DistilBERT
Sentiment labels from RoBERTa
Final model comparison table
```

## Testing

The project currently does not include a complete automated unit test suite.

However, a basic GitHub Actions CI workflow has been added. The workflow checks that:

```text
The repository can be checked out
Python 3.10 can be installed
Dependencies can be installed from requirements.txt
Main.ipynb exists
requirements.txt exists
```

The workflow file is located at:

```text
.github/workflows/ci.yml
```

Developers should also manually validate the notebook before opening a Pull Request.

Manual validation steps:

```text
Open Main.ipynb
Run all cells from top to bottom
Check that the dataset loads correctly
Check that preprocessing runs without errors
Check that sentiment models generate predictions
Check that the final evaluation table is produced
```

## Contribution Workflow

The project follows a simple Git feature-branch workflow.

Update the main branch:

```bash
git checkout main
git pull origin main
```

Create a new feature branch:

```bash
git checkout -b feature/new-feature
```

Examples:

```text
feature/add-new-model
feature/improve-preprocessing
fix/dataset-path-error
docs/update-user-guide
```

After making changes, check the modified files:

```bash
git status
```

Stage the files:

```bash
git add .
```

Commit the changes:

```bash
git commit -m "feat: add new sentiment model"
```

Push the branch:

```bash
git push --set-upstream origin feature/new-feature
```

Then open a Pull Request on GitHub.

## Commit Message Convention

Developers should use clear and consistent commit messages.

Recommended format:

```text
type: short description
```

Examples:

```text
feat: add aspect extraction step
fix: correct dataset loading path
docs: update user guide
docs(developer-guide): add developer guide
docs(cicd): update CI/CD section
ci: add GitHub Actions workflow
refactor: simplify preprocessing function
```

Recommended prefixes:

```text
feat: new feature
fix: bug fix
docs: documentation update
ci: CI/CD-related change
refactor: code restructuring
chore: maintenance task
```

## CI/CD Rules

The project uses a basic GitHub Actions CI workflow.

The workflow runs on:

```text
push to main
pull request to main
manual workflow_dispatch
```

The workflow uses an Ubuntu runner, checks out the repository, sets up Python 3.10, installs dependencies, and validates the main project files.

Developers should make sure the CI workflow passes before considering a change complete. If the workflow fails, the developer should inspect the GitHub Actions logs, fix the issue, and push a new commit.

## Secrets and Environment Variables

The current version of the project does not require private API keys, database credentials, or protected deployment tokens.

Since Amazon scraping was postponed, no Amazon-related credential is required.

If future versions add real-time scraping, external APIs, or private datasets, sensitive values must not be committed to the repository. They should be stored as GitHub Secrets or local environment variables.

Examples of values that must not be committed:

```text
API keys
Access tokens
Passwords
Private dataset links
Personal file paths
```

## Development Tools

Recommended development tools:

```text
Visual Studio Code
Jupyter Notebook
JupyterLab
Git
GitHub
```

Useful command-line commands:

```bash
git status
git pull
git checkout -b feature/example
git add .
git commit -m "docs: update developer guide"
git push
pip install -r requirements.txt
```

Developers using VS Code should select the correct Python interpreter, preferably the virtual environment created for the project.

## Future Improvements

The developer workflow can be improved by adding more structure and automation.

Possible future improvements include:

```text
Move reusable notebook logic into separate Python modules
Add unit tests for preprocessing functions
Add automated notebook execution in CI
Add linting and formatting checks
Add a data/ folder with clear dataset instructions
Add a build matrix for multiple Python versions
Improve README instructions for local execution
```

These improvements would make the project easier to maintain and more suitable for collaborative development.
