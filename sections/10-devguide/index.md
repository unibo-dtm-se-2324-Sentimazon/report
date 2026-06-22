---
title: Developer guide
has_children: false
nav_order: 11
---


# User Guide

This section explains how to use the Sentimazon project from the user perspective, assuming that the project has already been downloaded and installed. Sentimazon is a Python-based sentiment analysis tool developed using a Jupyter Notebook and reusable Python modules. The goal of the project is to analyze product reviews and extract useful information about customer opinions. The analysis focuses on mobile phone reviews and applies different sentiment analysis methods, including VADER, DistilBERT, and RoBERTa.

## Accessing the Project

To use the project, first download or clone the GitHub repository:

```bash
git clone https://github.com/unibo-dtm-se-2324-Sentimazon/Sentimazon-Project.git
```

Then move into the project folder:

```bash
cd Sentimazon-Project
```

The project can be opened using Visual Studio Code, Jupyter Notebook, or JupyterLab.

The main files and folders required to use the project are:

| File or folder | Purpose |
|---|---|
| `notebooks/Main.ipynb` | Main notebook used to run the analysis workflow |
| `src/sentimazon` | Python package containing the reusable project modules |
| `data` | Folder containing the review dataset |
| `requirements.txt` | List of required Python libraries |
| `README.md` | General project documentation |
| `tests` | Automated tests for the main lightweight modules |

## Installing Dependencies

Before running the notebook, install the required Python packages. From the project folder, run:

```bash
pip install -r requirements.txt
```

This installs the libraries needed for data loading, preprocessing, visualization, Natural Language Processing, sentiment analysis, and evaluation.

The project uses libraries such as:

- Pandas
- NumPy
- NLTK
- Matplotlib
- scikit-learn
- Transformers

Some NLTK resources may also need to be downloaded before running the full workflow. These resources are used for stop-word removal, tokenization, lemmatization, part-of-speech tagging, and VADER sentiment analysis.

They can be downloaded from a Python cell using:

```python
import nltk

nltk.download("stopwords")
nltk.download("punkt")
nltk.download("wordnet")
nltk.download("vader_lexicon")
nltk.download("averaged_perceptron_tagger")
```

## Dataset Preparation

The project was originally planned to perform real-time sentiment analysis on Amazon reviews using an Amazon review scraper. However, due to Amazon policy limitations and scraping restrictions, the scraping component was postponed. Instead, a Kaggle mobile review sentiment dataset was used to make the project more stable and reproducible.

The dataset contains customer reviews and sentiment labels. The main columns used by the project are:

| Column | Description |
|---|---|
| `review_text` | The original written product review |
| `sentiment` | The original sentiment label, such as positive, negative, or neutral |

In the revised version of the project, the dataset is stored inside the project `data` folder. The notebook uses a relative path instead of an absolute path, which makes the project easier to run on another machine.

The data loading step uses the dataset from:

```text
data/Mobile_Reviews_Sentiment.csv
```

## Running the Notebook

Open the main notebook:

```text
notebooks/Main.ipynb
```

Then run the notebook cells from top to bottom.

The notebook follows these main steps:

1. Load the review dataset.
2. Select the review text and sentiment columns.
3. Clean the review texts.
4. Remove stop words.
5. Tokenize the comments.
6. Lemmatize the tokens.
7. Apply part-of-speech tagging.
8. Extract product aspects.
9. Apply sentiment analysis models.
10. Evaluate model performance.
11. Visualize the results.

Users should run the notebook sequentially because later steps depend on the output of earlier steps.

## Text Preprocessing

The first part of the notebook prepares the review text for analysis.

The preprocessing includes:

- Removing usernames or unnecessary symbols
- Removing links
- Removing hashtags
- Removing special characters
- Converting text to lowercase
- Removing stop words
- Tokenizing words
- Lemmatizing words
- Applying part-of-speech tagging

This step is important because raw customer reviews usually contain noise. Cleaning the text makes the sentiment analysis more reliable and easier to interpret.

## Aspect Extraction

After preprocessing, the notebook extracts product-related aspects from the reviews.

The main product aspects considered in the project are:

- Battery
- Price
- Quality
- Performance

The system searches for these aspect words inside the cleaned review text and creates a table containing the related review, the original sentiment label, and the detected aspect.

This allows the user to understand not only whether a review is positive or negative, but also which product feature the opinion refers to.

## Sentiment Analysis Models

The notebook applies different sentiment analysis approaches: VADER, DistilBERT, and RoBERTa.

### VADER

VADER is a lexicon-based sentiment analysis method. It calculates a sentiment score for each review and classifies it as positive, negative, or neutral based on the compound score.

The notebook uses VADER to generate columns such as:

```text
vader_sentiment
vader_label
```

### DistilBERT

DistilBERT is a transformer-based model used for sentiment classification. It predicts whether each review is positive or negative and provides a confidence score.

The notebook applies DistilBERT to the extracted review-aspect data and stores the predicted sentiment.

### RoBERTa

RoBERTa is another transformer-based sentiment analysis model. It is used to classify the sentiment of the reviews and compare its results with the other approaches.

By using multiple models, the project allows users to compare a traditional lexicon-based sentiment analysis method with transformer-based methods.

## Model Evaluation

After applying the sentiment analysis models, the notebook compares their performance using common evaluation metrics:

- Accuracy
- Precision
- Recall
- F1-score

These metrics help users understand how well each model performs compared with the original sentiment labels in the dataset.

The final model comparison table includes:

- VADER
- DistilBERT
- RoBERTa

## Output Interpretation

The final outputs of the notebook include:

- Cleaned review data
- Tokenized and lemmatized comments
- Extracted product aspects
- Sentiment predictions from VADER
- Sentiment predictions from DistilBERT
- Sentiment predictions from RoBERTa
- Model performance comparison table
- Visualization charts

The user can use these outputs to understand customer opinions about different product aspects. For example, if many negative reviews are associated with battery or performance, this may indicate product areas that need improvement.

## Running Automated Tests

The project also includes automated tests for the main lightweight modules. To run the tests locally on PowerShell, use:

```bash
$env:PYTHONPATH="src"
python -m pytest
```

The current local test result is:

```text
7 passed
```

The tests cover:

- Data loading
- Text preprocessing
- Aspect extraction
- Evaluation metrics

Transformer-based sentiment models such as DistilBERT and RoBERTa are not included in the automated tests because they require heavier dependencies and model downloads.

## Notes and Limitations

The current version of Sentimazon uses a static dataset instead of real-time Amazon scraping. This makes the project easier to reproduce, but it means that the analysis is limited to the dataset used in the notebook.

The project also requires the dataset file to be available in the correct location inside the `data` folder. If the file is missing or the path is incorrect, the data loading step will fail.

Transformer-based models such as DistilBERT and RoBERTa may take longer to run than VADER, especially on a normal laptop without GPU acceleration. During the first execution, these models may also need to be downloaded through the `transformers` library.
````
