---
title: CI/CD
has_children: false
nav_order: 9
---

# CI/CD

The Continuous Integration/Continuous Deployment (CI/CD) workflow for the Sentimazon project supports the automation of project validation and documentation deployment. Since the project is mainly developed as a Python-based sentiment analysis tool using Jupyter Notebook, the CI/CD process focuses on reproducibility, dependency installation, project validation, and report publication.

## Continuous Integration

Continuous Integration is used to check whether the project remains executable and consistent after changes are pushed to the repository. In this project, CI can automate tasks such as setting up the Python environment, installing the required dependencies from requirements.txt, and checking that the main notebook and project files are correctly available.

This is important because the project depends on several Python libraries, including pandas, nltk, matplotlib, scikit-learn, and transformers. Automating these checks helps detect missing packages, dependency problems, or broken project structure earlier in the development process.

The project was originally planned to perform real-time sentiment analysis on Amazon reviews using an Amazon review scraper. However, due to Amazon’s updated policies and scraping limitations, the scraping component was postponed. Therefore, the project uses a Kaggle dataset to continue the analysis in a more stable and reproducible way.

The analysis pipeline includes loading the dataset, cleaning review texts, removing stop words, tokenization, lemmatization, part-of-speech tagging, aspect extraction, and sentiment analysis. Product aspects such as battery, price, quality, and performance are extracted from the reviews. Then, different sentiment analysis models, including VADER, DistilBERT, and RoBERTa, are applied and compared using accuracy, precision, recall, and F1-score.

## Continuous Deployment

Continuous Deployment is mainly related to the publication of the project report. Instead of deploying a production web application, the project uses GitHub Pages to make the report available online.

This is useful because it allows the documentation to stay synchronized with the repository. When the report is updated, the published version can also be updated automatically, reducing manual work and making the project easier to review.

## GitHub Actions Implementation

GitHub Actions is used to support the CI/CD workflow. The workflows are defined using YAML files stored in the .github/workflows directory of the repository. These workflow files describe when the automation should run, which operating system should be used, and which commands should be executed.

A typical workflow for this project includes checking out the repository, setting up Python, installing dependencies from requirements.txt, and running validation steps. For deployment, GitHub Actions can be used together with GitHub Pages to publish the report automatically.

The project does not currently require complex secrets because it does not use private APIs, databases, or protected external services. Since the Amazon scraping component was postponed, no Amazon-related API key or credential is required. If external APIs are added in the future, sensitive values should be stored securely as GitHub repository secrets and accessed through environment variables inside the workflow.

Overall, CI/CD improves the maintainability and reproducibility of the Sentimazon project. It reduces manual work, helps detect technical problems earlier, and ensures that the project report remains accessible and synchronized with the repository.