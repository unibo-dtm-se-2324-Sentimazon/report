---
title: Development
has_children: false
nav_order: 5
---

# Development

The project is followed a data-centric and iterative strategy, focusing on reliability, modular desining, and reprouciablity. The first intention of the project was to implement an scraper to capture reviews from amazon website related to the target-product. However, the recent policies and limitations of amazon website regarding to data privacy protextion have hinder the project to achive its initaial goal.
Therefore, the publicly available amazon reviews from Kaggle website is used to not only consider the data from amazon website but also compliance with amazon data privacy and usage. The dataset cosnist of about 25400 reviews, mostly on English, as input of the project, providing adequate data for further computations. This transitions leads to development of relaiable NLP pipeline for processing and anlysing unstructured data to extract meanful insghts.

## Development strategy

Sentimazon is implemented using Python and executed mainly through a Jupyter Notebook. The notebook is used as the execution interface, while the main logic is organized into reusable Python modules. This structure makes the workflow easier to understand, maintain, and test.

Dependency management is handled through the `requirements.txt` file, which lists the libraries needed to run the project. The main libraries used in the project are:

- **Pandas:** loading, manipulating, and storing structured review data
- **NLTK:** preprocessing text and supporting sentiment analysis tasks
- **Matplotlib:** visualizing aspect frequency and model performance
- **Regular Expressions:** cleaning unstructured textual data and removing noise
- **scikit-learn:** calculating evaluation metrics such as accuracy, precision, recall, and F1-score
- **Transformers:** applying transformer-based sentiment models such as DistilBERT and RoBERTa
The development process was improved after the project revision. The first version concentrated most of the implementation in the notebook. In the revised version, the code was separated into modules under `src/sentimazon`, while the notebook remained responsible for running the workflow and showing the results.

## Distributed Version Control System (DVCS)

The Sentimazon project uses Git as its Distributed Version Control System. Git was used to track the history of changes, manage the development process, and provide a clear record of how the project evolved.

In the first version, most development was done directly on the main branch. After the project review, the workflow was improved by creating a separate branch called `project-revision`. The main refactoring work was completed on this branch and then merged into `main` through Pull Request #5 after CI validation.

This improved workflow made the development process clearer and more traceable. It also shows the use of a more standard Software Engineering process:

```text
branch → commits → automated tests → CI validation → pull request → merge → release
```
## Commit Conventions

The project is used free-form messages in order to commit thoughat the changes without restricted structure. While the most of the project is followed the free-form commiting, the developer of the project relaizedd the cimmiting can be even more clearer if the convicetional commiting be use. Therefore, about midlle of the commits, the project is followed the following format for rest of the project. The project is followed the conventional commits specifications:
`<type>(<scope>): <short description>`
This form of cimmiting create a clear and traciable changes, providing a standardized format for commit messages. In this regards, it makes easier for developers to tract the history of the commits to understand the form of the commit and the changes related to it. Typical commit types including feat, fix, refactor, and docs as part of the format of commiting.

## Implementation

A list of sequential Natural language procrssing pipeline is created in order to initiate and process specific part of the the data manipulation for analysis. The project is inistate to excecute using the main notebook (Main.ipyb), which starting to lead the data and proceed the aspect based sentiment analysis. This initate prcosssing sequnces of phases that conduct part of compuations on the data based on the input dataset. Reading the stored data in a CSV file, including reviews from outside sources like Kaggle, is the responsibility of the first step, data acuaistion. To facilitate the normalization of the textual data and eliminate noise from subsequent analysis, the pre-processing step is carried out in the following step. After preprocessing, the sentiment associated with each aspect of sentiment is extracted using aspect-based sentiment analysis. Three categories—positive, negative, and neutral—are used to classify the sentiments. In order to display the sentiment distributions and aspect frequency, the visualization components are created as graphical charts in the last step.
In the revised implementation, these steps are no longer concentrated only inside the notebook. They are distributed across separate modules:

| Module | Responsibility |
|---|---|
| `data_loader.py` | Loads the dataset and selects required columns |
| `preprocessing.py` | Cleans, tokenizes, and lemmatizes review text |
| `aspect_extraction.py` | Applies POS tagging and extracts nouns/aspects |
| `sentiment_analysis.py` | Runs VADER, DistilBERT, and RoBERTa sentiment models |
| `evaluation.py` | Calculates model performance metrics |
| `visualization.py` | Generates plots and charts |

This implementation improves modularity because each file has a clear responsibility. It also improves testability because the main functions can be tested independently from the notebook.
