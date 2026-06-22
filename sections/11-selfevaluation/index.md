---
title: Self-evaluation
has_children: false
nav_order: 12
---

# Self-evaluation

## Morteza Sheykhizadeh

During this project, I worked on the development and revision of Sentimazon, a Python-based sentiment analysis project focused on analyzing mobile phone reviews. The project was initially planned to perform real-time sentiment analysis on Amazon reviews using a review scraper. However, due to Amazon policy limitations and scraping restrictions, the scraping component was postponed, and a publicly available mobile review sentiment dataset was used instead. This made the project more stable, reproducible, and easier to execute in a controlled environment.

After receiving feedback on the first version of the project, I revised the repository to better reflect Software Engineering practices. The first version was mainly implemented inside a Jupyter Notebook, while the revised version separates the main logic into reusable Python modules, adds automated tests, updates the CI workflow, and includes a clearer GitHub development workflow.

## Role and Contributions

My role in the project was focused on the data analysis pipeline, notebook implementation, code refactoring, documentation, testing, and CI configuration.

My main contributions were:

- Prepared and used the mobile review sentiment dataset
- Implemented text cleaning and preprocessing steps
- Removed stop words from review texts
- Applied tokenization and lemmatization
- Used part-of-speech tagging for keyword and aspect extraction
- Extracted product-related aspects such as battery, price, quality, and performance
- Applied VADER sentiment analysis
- Applied transformer-based sentiment analysis using DistilBERT and RoBERTa
- Compared model performance using accuracy, precision, recall, and F1-score
- Refactored the notebook logic into reusable Python modules under `src/sentimazon`
- Replaced the absolute dataset path with a relative project path
- Added automated tests using `pytest`
- Updated the GitHub Actions workflow to run automated tests
- Used a separate `project-revision` branch for the revised implementation
- Created and merged Pull Request #5 after CI validation
- Published release `v1.0.0`
- Updated the User Guide, Developer Guide, CI/CD documentation, and other report sections

The notebook remains the main execution interface, but the core project logic is now separated into modules such as `data_loader.py`, `preprocessing.py`, `aspect_extraction.py`, `sentiment_analysis.py`, `evaluation.py`, and `visualization.py`.

## Strengths of the Product

One strength of Sentimazon is that the analysis pipeline is clear and easy to follow. The workflow moves step by step from dataset loading to preprocessing, aspect extraction, sentiment analysis, evaluation, and visualization.

Another strength is that the project compares different sentiment analysis approaches. VADER provides a simple lexicon-based method, while DistilBERT and RoBERTa provide transformer-based alternatives. This makes the comparison more informative than relying on only one model.

The use of a fixed dataset improves reproducibility. Since real-time Amazon scraping was postponed, the project does not depend on unstable external website access or scraping restrictions.

A major improvement in the revised version is the project structure. The original notebook-based implementation was refactored into a modular Python package under `src/sentimazon`. This makes the project easier to understand, maintain, and extend.

The project also includes automated tests using `pytest`. These tests validate the main lightweight modules, including data loading, preprocessing, aspect extraction, and evaluation. The current local test result is:

```text
7 passed
```

The GitHub Actions CI workflow was also improved. Instead of only checking whether files exist, the CI workflow now runs the automated test suite. This provides automatic validation for future pushes and pull requests.

## Weaknesses and Limitations

The main limitation of the project is that it does not currently perform real-time Amazon review scraping. This means that the system analyzes a static dataset instead of live user reviews. However, this decision also improved reproducibility and avoided problems related to scraping restrictions.

Another limitation is that the project is still mainly executed through a Jupyter Notebook. Although the main logic has been moved into reusable modules, the project is not yet a full standalone software application with a graphical interface or web interface.

The automated tests cover the main lightweight functions, but they do not cover every function in the project. Transformer-based models such as DistilBERT and RoBERTa are not included in the automated tests because they require heavier dependencies and model downloads. Including them in the CI workflow could make the tests slower or less stable.

The project also does not use a database or a deployed web application. The dataset is stored locally as a CSV file, which is suitable for the current educational version but may not be enough for a larger production-oriented system.

Finally, transformer-based models may take a long time to run on a normal laptop without GPU acceleration.

## My Strengths During the Project

During the project, I improved my practical skills in Python, Natural Language Processing, and sentiment analysis. I was able to build a complete workflow from raw review text to final model evaluation and visualization.

I also improved my understanding of Software Engineering practices. In the revised version of the project, I worked on modularity, testing, CI, version control, pull requests, releases, and documentation.

Another strength was adapting the project when the original scraping idea became difficult. Instead of stopping the work, I changed the approach and used a dataset-based solution to keep the project feasible and reproducible.

The revision process also helped me understand the difference between a data analysis notebook and a more structured software project. I learned that a project should not only produce results, but should also be maintainable, testable, documented, and reproducible.

## Areas for Improvement

There are several areas where I could improve the project further.

First, I could add more automated tests for additional functions. The current tests cover the main lightweight modules, but more tests could be added for edge cases, data validation, and visualization outputs.

Second, I could improve the CI workflow by adding linting and formatting checks. This would help keep the code style more consistent.

Third, I could add automated notebook execution to the CI workflow. This would allow GitHub Actions to check whether the full notebook can run successfully from beginning to end.

Fourth, I could improve the project structure further by creating a command-line interface. This would allow users to run the pipeline without opening the notebook.

Finally, I could improve the data collection strategy in the future by using a legal and stable external API or another approved data source instead of scraping.

## Final Reflection

This project helped me understand that Software Engineering is not only about writing code that works. A good software project also needs clear structure, documentation, reproducible setup, version control, testing, CI/CD, and a workflow that other people can understand and follow.

Through Sentimazon, I improved my skills in text preprocessing, sentiment analysis, model comparison, GitHub, documentation, testing, and CI/CD. I also learned how important it is to adapt the project scope when technical or external limitations appear.

The most important lesson from the revision was that a notebook can be useful for experimentation, but it is not enough by itself to demonstrate good Software Engineering practice. By moving the code into modules, adding tests, updating CI, using a branch and pull request workflow, and publishing a release, the project became more structured and maintainable.

Overall, this project was a useful experience because it combined data analysis with Software Engineering practices. It helped me understand how to build, document, validate, and revise a small but complete sentiment analysis system.
````
