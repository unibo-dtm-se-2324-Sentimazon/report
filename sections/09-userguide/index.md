---
title: User guide
has_children: false
nav_order: 10
---

# User Guide

This section explains how to use the Sentimazon project from the user perspective, assuming that the project has been correctly downloaded and installed.
Sentimazon is a Python-based sentiment analysis tool developed in Jupyter Notebook. The goal of the project is to analyze product reviews and extract useful information about customer opinions. The analysis focuses on mobile phone reviews and applies different sentiment analysis methods, including VADER, DistilBERT, and RoBERTa.

## Accessing the Project
To use the project, first download or clone the GitHub repository:
git clone https://github.com/unibo-dtm-se-2324-Sentimazon/Sentimazon-Project.git
Then open the project folder in Visual Studio Code, Jupyter Notebook, or JupyterLab.
The main files required to use the project are:
Main.ipynb
requirements.txt
README.md
Main.ipynb contains the main analysis pipeline.
requirements.txt contains the Python libraries required to run the project.
README.md provides a general description of the project.

## Installing Dependencies
Before running the notebook, install the required Python packages. From the project folder, run:
pip install -r requirements.txt
This installs the libraries needed for data loading, preprocessing, visualization, natural language processing, and sentiment analysis.
The project uses libraries such as:
pandas
nltk
matplotlib
scikit-learn
transformers
Some NLTK resources may also need to be downloaded when running the notebook, such as stop words, tokenizers, WordNet, and the POS tagger.

## Dataset Preparation
The project was originally planned to perform real-time sentiment analysis on Amazon reviews using an Amazon review scraper. However, due to Amazon policy limitations and scraping restrictions, the scraping component was postponed. Instead, a Kaggle dataset was used to make the project more stable and reproducible.
The dataset used in the notebook is a mobile review sentiment dataset. It contains customer reviews and sentiment labels. The main columns used by the project are:
review_text
sentiment
The review_text column contains the written review.
The sentiment column contains the original sentiment label, such as Positive, Negative, or Neutral.
Before running the notebook, make sure the dataset file is available and that the file path inside the notebook is correct. If the dataset is stored in a different location, update the path in the data loading cell.
Example:
data = pd.read_csv("Mobile_Reviews_Sentiment.csv")

## Running the Notebook
Open the file:
Main.ipynb
Then run the notebook cells from top to bottom.
The notebook follows these main steps:
Load the dataset
Select the review text and sentiment columns
Clean the review texts
Remove stop words
Tokenize the comments
Lemmatize the tokens
Apply part-of-speech tagging
Extract product aspects
Apply sentiment analysis models
Compare model performance
Users should run the notebook sequentially because later steps depend on the output of earlier steps.

## Text Preprocessing
The first part of the notebook prepares the review text for analysis.
The preprocessing includes:
Removing usernames or unnecessary symbols
Removing links
Removing hashtags
Removing special characters
Converting text to lowercase
Removing stop words
Tokenizing words
Lemmatizing words
Applying part-of-speech tagging
This step is important because raw customer reviews usually contain noise. Cleaning the text makes the sentiment analysis more reliable and easier to interpret.

## Aspect Extraction
After preprocessing, the notebook extracts product-related aspects from the reviews.
The main product aspects considered in the project are:
battery
price
quality
performance
The system searches for these aspect words inside the cleaned review text and creates a new table containing the related review, the original sentiment label, and the detected aspect.
This allows the user to understand not only whether a review is positive or negative, but also which product feature the opinion refers to.
For example, the analysis can help answer questions such as:
Are customers satisfied with battery life?
Are users complaining about price?
Is product quality mentioned positively or negatively?
How do users describe performance?

## Sentiment Analysis Models
The notebook applies different sentiment analysis approaches.
VADER
VADER is a lexicon-based sentiment analysis method. It calculates a sentiment score for each review and classifies it as positive, negative, or neutral based on the compound score.
The notebook uses VADER to generate:
vader_sentiment
vader_label
DistilBERT
DistilBERT is a transformer-based model used for sentiment classification. It predicts whether each review is positive or negative and provides a confidence score.
The notebook applies DistilBERT to the extracted review-aspect data and stores the predicted sentiment.
RoBERTa
RoBERTa is another transformer-based sentiment analysis model. It is also used to classify the sentiment of the reviews and compare its results with the other approaches.
By using multiple models, the project allows users to compare traditional lexicon-based sentiment analysis with transformer-based methods.

## Model Evaluation
After applying the sentiment analysis models, the notebook compares their performance using common evaluation metrics:
Accuracy
Precision
Recall
F1-score
These metrics help users understand how well each model performs compared with the original sentiment labels in the dataset.
The final model comparison table includes:
VADER
DistilBERT
RoBERTa
The user can inspect this table to identify which model performed better for the selected dataset and analysis conditions.
## Output Interpretation
The final outputs of the notebook include:
Cleaned review data
Tokenized and lemmatized comments
Extracted product aspects
Sentiment predictions from VADER
Sentiment predictions from DistilBERT
Sentiment predictions from RoBERTa
Model performance comparison table
The user can use these outputs to understand customer opinions about different product aspects. For example, if many negative reviews are associated with battery or performance, this may indicate areas where the product needs improvement.

## Notes and Limitations

The current version of Sentimazon uses a static dataset instead of real-time Amazon scraping. This makes the project easier to reproduce, but it means that the analysis is limited to the dataset used in the notebook. The project also requires the dataset file path to be correctly configured before running the notebook. If the file path is incorrect, the data loading step will fail.
Finally, transformer-based models such as DistilBERT and RoBERTa may take longer to run than VADER, especially on a normal laptop without GPU acceleration.