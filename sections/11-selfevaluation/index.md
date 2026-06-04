---
title: Self-evaluation
has_children: false
nav_order: 12
---

# Self-evaluation

## Morteza Sheykhizadeh

During this project, I worked on the development of Sentimazon, a Python-based sentiment analysis project focused on analyzing mobile phone reviews. The project was initially planned to perform real-time sentiment analysis on Amazon reviews using a review scraper. However, due to Amazon policy limitations and scraping restrictions, the scraping component was postponed, and a Kaggle dataset was used instead to keep the project reproducible and stable.

## Role and Contributions

My role in the project was mainly focused on the data analysis pipeline, notebook implementation, documentation, and basic CI configuration.

My main contributions were:

```text
Prepared and used the mobile review sentiment dataset
Implemented text cleaning and preprocessing steps
Removed stop words from review texts
Applied tokenization and lemmatization
Used part-of-speech tagging for keyword extraction
Extracted product-related aspects such as battery, price, quality, and performance
Applied VADER sentiment analysis
Applied transformer-based sentiment analysis using DistilBERT and RoBERTa
Compared model performance using accuracy, precision, recall, and F1-score
Updated the User Guide, Developer Guide, and CI/CD documentation
Added a basic GitHub Actions workflow for project validation
```

The main implementation work was done in `Main.ipynb`, where the complete sentiment analysis pipeline was developed and executed. I also contributed to improving the report structure and making the project easier to understand for both users and developers.

## Strengths of the Product

One strength of Sentimazon is that the analysis pipeline is clear and easy to follow. The notebook moves step by step from dataset loading to preprocessing, aspect extraction, sentiment analysis, and model evaluation.

Another strength is that the project compares different sentiment analysis approaches. VADER provides a simple lexicon-based method, while DistilBERT and RoBERTa provide transformer-based alternatives. This makes the comparison more informative than relying on only one model.

The use of a fixed Kaggle dataset also improves reproducibility. Since real-time Amazon scraping was postponed, the project does not depend on unstable external website access.

The project also includes a basic GitHub Actions CI workflow. Although it is simple, it helps validate that the repository can be checked out, Python can be set up, dependencies can be installed, and the main project files exist.

## Weaknesses and Limitations

The main limitation of the project is that it does not currently perform real-time Amazon review scraping. This means that the system analyzes a static dataset instead of live user reviews.

Another limitation is that the project is notebook-based. This is useful for experimentation and explanation, but it is less structured than a full software application with separated Python modules and automated tests.

The current CI workflow is also basic. It checks dependency installation and file availability, but it does not yet run the full notebook or validate the model outputs automatically.

Transformer-based models such as DistilBERT and RoBERTa can also take a long time to run, especially on a normal laptop without GPU acceleration.

Finally, the dataset path must be managed carefully. If the notebook uses an absolute local path, other developers may not be able to run it without modifying the path.

## My Strengths During the Project

During the project, I improved my practical skills in Python, natural language processing, and sentiment analysis. I was able to build a complete pipeline from raw review text to final model evaluation.

I also learned how to connect software engineering practices with a data analysis project. For example, I worked on documentation, GitHub workflow, CI/CD, and repository organization.

Another strength was adapting the project when the original scraping idea became difficult. Instead of stopping the work, I changed the approach and used a dataset-based solution to keep the project feasible and reproducible.

## Areas for Improvement

There are several areas where I could improve the project further.

First, I could move reusable functions from the notebook into separate Python files. This would make the code cleaner and easier to maintain.

Second, I could add unit tests for preprocessing, aspect extraction, and sentiment analysis functions. This would improve reliability and make future changes safer.

Third, I could improve the CI workflow by adding automated notebook execution. This would allow GitHub Actions to check whether the notebook can run successfully from beginning to end.

Finally, I could improve the data collection strategy in the future by using a legal and stable external API or another approved data source instead of scraping.

## Final Reflection

This project helped me understand that software engineering is not only about writing code. A good project also needs clear documentation, reproducible setup, version control, CI/CD, and a structure that other people can understand and use.

Through Sentimazon, I improved my skills in text preprocessing, sentiment analysis, model comparison, GitHub, documentation, and basic CI/CD. I also learned how important it is to adapt the project scope when technical or external limitations appear.

Overall, this project was a useful experience because it combined data analysis with software engineering practices. It helped me understand how to build, document, and validate a small but complete sentiment analysis system.
````
