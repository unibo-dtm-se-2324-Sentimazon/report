---
title: Requirements
has_children: false
nav_order: 3
---
# Requirements

This section defines the main requirements of the Sentimazon project, including user stories, functional requirements, non-functional requirements, implementation requirements, acceptance criteria, and definition of done.

Sentimazon is a Python-based sentiment analysis project for analyzing mobile product reviews. The project loads review data, preprocesses text, extracts product-related aspects, applies sentiment analysis models, evaluates the results, and visualizes the output.

The original idea was to analyze Amazon reviews directly. However, due to scraping restrictions and reproducibility issues, the project was adapted to use a public mobile review sentiment dataset. This kept the main objective of customer review analysis while making the project easier to run and validate.

## User Stories

### Persona 1: Data Analyst

The data analyst is a technical user who wants to process and analyze customer review data.

- As a data analyst, I want to load a review dataset, so that I can analyze customer opinions.
- As a data analyst, I want to preprocess review text, so that the data is cleaner and more suitable for analysis.
- As a data analyst, I want to extract product aspects, so that I can understand which features are frequently mentioned.
- As a data analyst, I want to apply sentiment analysis models, so that I can classify reviews as positive, negative, or neutral.
- As a data analyst, I want to compare model performance, so that I can evaluate the results.
- As a data analyst, I want to visualize the output, so that I can present the results clearly.

### Persona 2: Business Decision Maker

The business decision maker is a non-technical stakeholder who wants to understand customer perception.

- As a business decision maker, I want to see frequent product aspects, so that I can understand what customers discuss most.
- As a business decision maker, I want to see sentiment results, so that I can understand customer satisfaction.
- As a business decision maker, I want visual summaries, so that I can identify product strengths and weaknesses quickly.

## Requirements Analysis

The requirements are divided into three groups:

- Functional requirements: what the system must do
- Non-functional requirements: quality expectations of the system
- Implementation requirements: technical constraints and development choices

Each requirement includes a short acceptance criterion and a definition of done. This connects the requirements to the validation process.

## Functional Requirements

| ID | Requirement | Acceptance criterion | Definition of done |
|---|---|---|---|
| FR1 | The system must load the review dataset. | The dataset is loaded from the project `data` folder. | The dataset loads successfully using `data_loader.py`. |
| FR2 | The system must select the required columns. | The workflow uses `review_text` and `sentiment`. | The selected DataFrame contains the required columns. |
| FR3 | The system must preprocess review text. | Text is cleaned, normalized, tokenized, and lemmatized. | Preprocessing is implemented in `preprocessing.py` and runs in the notebook. |
| FR4 | The system must extract product aspects. | Product-related terms such as battery, price, quality, and performance can be identified. | Aspect extraction is implemented in `aspect_extraction.py`. |
| FR5 | The system must apply sentiment analysis. | VADER, DistilBERT, and RoBERTa can generate sentiment outputs. | Sentiment analysis is implemented in `sentiment_analysis.py`. |
| FR6 | The system must evaluate model performance. | Accuracy, precision, recall, and F1-score are calculated. | Evaluation is implemented in `evaluation.py` and tested. |
| FR7 | The system must visualize results. | Aspect frequency, sentiment results, and model performance can be displayed. | Visualization is implemented in `visualization.py`. |

## Non-Functional Requirements

| ID | Requirement | Acceptance criterion | Definition of done |
|---|---|---|---|
| NFR1 | Usability | The notebook and outputs are understandable. | The User Guide explains how to run the project. |
| NFR2 | Reproducibility | The project can be run on another machine. | Dataset path is relative and dependencies are listed in `requirements.txt`. |
| NFR3 | Reliability | The same dataset produces consistent outputs. | The notebook runs successfully with the provided dataset. |
| NFR4 | Maintainability | The code is modular and easy to modify. | Source code is organized under `src/sentimazon`. |
| NFR5 | Testability | Main lightweight modules can be tested automatically. | Tests are included in the `tests` folder and run with `pytest`. |

## Implementation Requirements

| ID | Requirement | Justification | Definition of done |
|---|---|---|---|
| IR1 | The project must be implemented in Python. | Python supports NLP, data analysis, and visualization libraries. | Code is implemented in the notebook and `src/sentimazon`. |
| IR2 | The project must use appropriate analysis libraries. | Libraries improve reliability and development efficiency. | Required libraries are listed in `requirements.txt`. |
| IR3 | The project must use Git and GitHub. | Version control improves traceability and project management. | The repository includes commits, branch workflow, pull request, and release. |
| IR4 | The project must include automated testing and CI. | Testing and CI help detect errors after changes. | Tests pass locally and GitHub Actions runs successfully. |

## Traceability Between Requirements and Validation

| Requirement | Implementation evidence | Validation evidence |
|---|---|---|
| FR1, FR2 | `data_loader.py` | `test_data_loader.py` |
| FR3 | `preprocessing.py` | `test_preprocessing.py` |
| FR4 | `aspect_extraction.py` | `test_aspect_extraction.py` |
| FR5 | `sentiment_analysis.py` | Notebook execution |
| FR6 | `evaluation.py` | `test_evaluation.py` |
| FR7 | `visualization.py` | Notebook output |
| NFR2 | Relative paths and `requirements.txt` | Local execution |
| NFR5 | `tests` folder | Local tests and GitHub Actions |
| IR4 | `.github/workflows/ci.yml` | Successful CI run |

## Glossary

| Term | Definition |
|---|---|
| Sentiment analysis | A Natural Language Processing task used to identify whether text expresses positive, negative, or neutral opinion |
| Preprocessing | Cleaning and transforming raw text into a format suitable for analysis |
| Tokenization | Splitting text into smaller units such as words or tokens |
| Lemmatization | Reducing words to their base form |
| Aspect extraction | Identifying product-related features or topics from review text |
| Visualization | Presenting data or results through charts and graphs |
| CI | Continuous Integration, an automated process that validates changes in the repository |
| Acceptance criterion | A condition used to check whether a requirement is satisfied |
| Definition of done | A condition that shows when a requirement is complete |