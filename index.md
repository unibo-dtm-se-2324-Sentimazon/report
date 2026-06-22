---
title: Home
layout: home
has_children: false
nav_order: 1
---

# Sentimazon

### Authors

- [Morteza Sheykhizadeh](mailto:morteza.sheykhizadeh@studio.unibo.it)

## Abstract

Sentimazon is a Python-based sentiment analysis project focused on processing and analyzing product review data. The original project idea was to collect Amazon reviews in real time, but due to policy and technical limitations related to scraping, the implementation was based on a mobile product review sentiment dataset instead.

The project applies Natural Language Processing techniques to clean and process review text. The workflow includes data loading, text cleaning, stop-word removal, tokenization, lemmatization, part-of-speech tagging, aspect extraction, sentiment analysis, model evaluation, and visualization. The sentiment analysis part includes VADER and transformer-based models such as DistilBERT and RoBERTa, while the evaluation compares model outputs using metrics such as accuracy, precision, recall, and F1-score.

After receiving feedback on the first version of the project, the repository was revised to better reflect Software Engineering practices. The original notebook-based implementation was reorganized into a modular Python package under src/sentimazon. The main logic was separated into reusable modules for data loading, preprocessing, aspect extraction, sentiment analysis, evaluation, and visualization. Automated tests were added using pytest, and the GitHub Actions workflow was updated to run the test suite automatically instead of only checking for file existence.

The final version of the project also uses a clearer GitHub workflow, including a separate development branch, incremental commits, automated testing, CI validation, a pull request, merge into the main branch, and a published release. Therefore, the project is not only a data analysis notebook, but also a more structured and maintainable Software Engineering project.

## Disclaimer (if needed)

During the preparation of this work, the author used Grammarly to check grammar and readability, and used online documentation, GitHub repositories, forums, and tutorials to solve technical issues and improve the implementation. ChatGPT was used as a support tool for debugging, idea clarification, code organization, and improving written explanations.

All generated or suggested content was reviewed, modified, and adapted by the author. The author takes full responsibility for the final report, source code, and project artifact.

