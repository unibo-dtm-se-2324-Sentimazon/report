---
title: Deployment
has_children: false
nav_order: 8
---

# Deployment

## System Requirements

The following software and tools are required to run the Sentimazon project locally:

- Python 3.9 or later
- Git
- pip
- Visual Studio Code with the Jupyter extension, or Jupyter Notebook
- Internet connection for the first execution of transformer-based models such as DistilBERT and RoBERTa

The main Python libraries used in the project are listed in the `requirements.txt` file.

## User Installation

### Step 1 – Clone the repository

The project repository is available on GitHub. It can be cloned using the following command:

```bash
git clone https://github.com/unibo-dtm-se-2324-Sentimazon/Sentimazon-Project.git
```

After cloning the repository, move into the project folder:

```bash
cd Sentimazon-Project
```

### Step 2 – Install project dependencies

Install the required libraries using the following command:

```bash
pip install -r requirements.txt
```

The main dependencies used in the project include:

- Pandas
- NumPy
- Matplotlib
- NLTK
- scikit-learn
- Transformers
- pytest

### Step 3 – Download required NLTK resources

Some NLTK resources are required for preprocessing and sentiment analysis. They can be downloaded from inside Python or from a notebook cell:

```python
import nltk

nltk.download("stopwords")
nltk.download("punkt")
nltk.download("wordnet")
nltk.download("vader_lexicon")
nltk.download("averaged_perceptron_tagger")
```

These resources are needed for stop-word removal, tokenization, lemmatization, part-of-speech tagging, and VADER sentiment analysis.

### Step 4 – Run the notebook

The project can be executed from Visual Studio Code with the Jupyter extension or directly from Jupyter Notebook.

Open the notebook located in:

```text
notebooks/Main.ipynb
```

The notebook executes the project workflow step by step:

1. Load the review dataset from the `data` folder.
2. Select the required columns for analysis.
3. Apply preprocessing, including text cleaning, stop-word removal, tokenization, and lemmatization.
4. Apply part-of-speech tagging.
5. Extract product-related aspects from the reviews.
6. Run sentiment analysis models:
   - VADER
   - DistilBERT
   - RoBERTa
7. Evaluate and compare model performance using:
   - Accuracy
   - Precision
   - Recall
   - F1-score
8. Visualize the results using charts and tables.

## Server-Side Installation

The Sentimazon project is mainly designed to run in a local environment. It does not require a web server, message broker, or external database.

The dataset is stored locally inside the project folder, and the analysis is executed through the notebook and Python modules. Therefore, no separate server-side installation is required for the current version of the project.

However, two transformer-based models, DistilBERT and RoBERTa, are loaded through the `transformers` library. During the first execution, these models may be downloaded automatically from the Hugging Face model repository. After the first download, they can usually be reused from the local cache.

## Running Automated Tests

The project includes automated tests written with `pytest`. These tests validate the main lightweight modules of the project.

To run the tests locally on PowerShell, use:

```bash
$env:PYTHONPATH="src"
python -m pytest
```

The current local test result is:

```text
7 passed
```

The automated tests cover:

- Data loading
- Text preprocessing
- Aspect extraction
- Evaluation metrics

Transformer-based sentiment models are not included in the automated tests because they require heavier dependencies and model downloads, which may make local and CI testing slower.

## Deployment Notes

The project is deployed as a GitHub repository rather than as a web application. The final version of the project includes:

- Source code under `src/sentimazon`
- Main notebook under `notebooks`
- Dataset under `data`
- Automated tests under `tests`
- CI workflow under `.github/workflows`
- Documentation pages
- GitHub release `v1.0.0`

The release version marks the stable revised version of the project after refactoring, testing, CI validation, pull request review, and merge into the `main` branch.