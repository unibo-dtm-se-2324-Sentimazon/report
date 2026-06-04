---
title: Developer guide
has_children: false
nav_order: 11
---

# Developer Guide

This section is intended for developers who want to contribute to the Sentimazon project or run it locally.

## Repository

```text
https://github.com/unibo-dtm-se-2324-Sentimazon/Sentimazon-Project
```

Report:

```text
https://unibo-dtm-se-2324-sentimazon.github.io/report/
```

## Issue Reporting

Issues should be reported on GitHub.

Use clear titles such as:

```text
Fix: dataset loading error
Fix: missing dependency
Feature: improve sentiment analysis
Feature: add notebook execution in CI
```

Each issue should include:

```text
Problem description
Steps to reproduce
Expected result
Actual result
Screenshot or error message, if needed
Python version and operating system
```

## Team Communication

Communication is handled through GitHub Issues and Pull Requests.

Maintainer:

```text
Morteza Sheykhizadeh
morteza.sheykhizadeh@studio.unibo.it
```

## Branch Naming

Use short and clear branch names.

```text
feature/add-new-model
feature/improve-preprocessing
fix/dataset-path-error
docs/update-report
ci/update-workflow
```

## Code Style

Python code should follow PEP 8 guidelines.

Use `snake_case` for functions and variables:

```python
def clean_comments(comment):
    ...
```

Use uppercase for constants:

```python
RELEVANT_ASPECTS = ["battery", "price", "quality", "performance"]
```

Avoid:

```text
Hardcoded local paths
Unused imports
Duplicated code
Private files or credentials
Large generated outputs
```

## File Organization

```text
Sentimazon-Project/
├── .github/
│   └── workflows/
│       └── ci.yml
├── Main.ipynb
├── requirements.txt
└── README.md
```

`Main.ipynb` contains the main sentiment analysis pipeline.  
`requirements.txt` contains the required Python dependencies.  
`.github/workflows/ci.yml` contains the GitHub Actions CI workflow.

## Development Setup

Install the required tools:

```text
Python 3.10 or higher
Git
pip
VS Code, Jupyter Notebook, or JupyterLab
```

Clone the repository:

```bash
git clone https://github.com/unibo-dtm-se-2324-Sentimazon/Sentimazon-Project.git
```

Move into the project folder:

```bash
cd Sentimazon-Project
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Activate it on Linux or macOS:

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## Running the Project

Open:

```text
Main.ipynb
```

Run the notebook cells from top to bottom.

The notebook pipeline includes:

```text
Dataset loading
Text cleaning
Stop-word removal
Tokenization
Lemmatization
Part-of-speech tagging
Aspect extraction
VADER sentiment analysis
DistilBERT sentiment analysis
RoBERTa sentiment analysis
Model evaluation
```

## Dataset Configuration

The project currently uses a Kaggle mobile review dataset instead of live Amazon scraping because scraping was postponed due to policy and access limitations.

Avoid absolute paths such as:

```python
data = pd.read_csv("E:\\Class\\software\\Mobile_Reviews_Sentiment.csv")
```

Use a relative path instead:

```python
data = pd.read_csv("Mobile_Reviews_Sentiment.csv")
```

or:

```python
data = pd.read_csv("data/Mobile_Reviews_Sentiment.csv")
```

## Testing

The project does not currently include a full unit test suite.

A basic GitHub Actions CI workflow checks that:

```text
The repository can be checked out
Python 3.10 can be installed
Dependencies can be installed
Main.ipynb exists
requirements.txt exists
```

Before opening a Pull Request, developers should run the notebook manually and check that the final evaluation table is produced.

## Pull Request Process

Create a branch:

```bash
git checkout -b feature/improve-preprocessing
```

Commit and push:

```bash
git status
git add .
git commit -m "feat: improve preprocessing"
git push --set-upstream origin feature/improve-preprocessing
```

Then open a Pull Request on GitHub.

The Pull Request should explain:

```text
What was changed
Why it was changed
How it was tested
Known limitations
```

## Commit Messages

Use clear commit messages.

```text
feat: add aspect extraction step
fix: correct dataset path
docs: update developer guide
docs(cicd): update CI/CD section
ci: update GitHub Actions workflow
```

## CI/CD

The project uses GitHub Actions for basic CI validation.

The workflow runs on:

```text
push to main
pull request to main
manual workflow_dispatch
```

Developers should make sure the CI workflow passes before merging changes.

## Future Improvements

```text
Move reusable code into Python modules
Add unit tests
Add automated notebook execution in CI
Add linting and formatting checks
Add a data folder with dataset instructions
Add a build matrix for multiple Python versions
```