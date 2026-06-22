---
title: Concept
has_children: false
nav_order: 2
---

## Concept

Sentimazon is a Python-based sentiment analysis project for processing and analyzing product review data. The project focuses on mobile product reviews and uses a publicly available review dataset instead of real-time Amazon scraping, due to policy and technical limitations related to web scraping.

The main idea of the project is to transform unstructured review text into a cleaner and more structured form that can be used for Natural Language Processing and sentiment analysis. The input reviews may contain punctuation, usernames, hashtags, noisy words, and other elements that are not useful for analysis. Therefore, the text is first cleaned and preprocessed before applying sentiment analysis and visualization.

The goal of Sentimazon is to support the analysis of customer opinions about product features. By processing product reviews, the project can help identify frequent product-related aspects, such as battery, price, quality, and performance, and evaluate whether reviews express positive, negative, or neutral sentiment.

### Type of Product

Sentimazon is not a graphical user interface application. It is a data processing and sentiment analysis toolkit implemented in Python. The project can be used through a Jupyter Notebook and reusable Python modules.

The project consists of:

1. A Python-based workflow for executing the sentiment analysis process from data loading to final results.
2. A Jupyter Notebook interface for running the workflow, inspecting intermediate results, and visualizing the analysis.
3. A modular Python package under `src/sentimazon`, where the main logic is separated into reusable components.

### Key Features

The main features of the project are:

- **Dataset processing:** Loading the review dataset and selecting the required columns for analysis.
- **Text preprocessing:** Cleaning the review text by removing unnecessary elements, converting text to lowercase, removing stop words, tokenizing words, and applying lemmatization.
- **Aspect extraction:** Extracting noun-based product aspects from the processed reviews to identify frequently mentioned product features.
- **Sentiment analysis:** Applying VADER and transformer-based sentiment models such as DistilBERT and RoBERTa to classify review sentiment.
- **Model evaluation:** Comparing sentiment analysis results using accuracy, precision, recall, and F1-score.
- **Visualization:** Presenting frequent aspects and model performance using basic charts.

### User Interactions and Applications

Sentimazon is designed as a single-user analytical tool. It does not require different user roles such as administrator, guest, or registered user. The user interacts with the project by running the notebook and Python modules.

The project can be used for educational purposes, academic coursework, and exploratory analysis of customer review datasets. It can also be adapted to other types of textual datasets, as long as the data is collected and used according to the relevant privacy, platform, and data usage policies.

### Technical Implementation

The project is implemented using Python. The main technologies used are:

- **Programming language:** Python
- **Core libraries:** Pandas, NumPy, Regex, and NLTK
- **Sentiment analysis tools:** VADER, DistilBERT, and RoBERTa
- **Evaluation:** scikit-learn
- **Visualization:** Matplotlib
- **Execution environment:** Jupyter Notebook and Python modules
- **Data source:** Publicly available mobile review sentiment dataset








