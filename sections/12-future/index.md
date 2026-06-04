---
title: Future work
has_children: false
nav_order: 13
---

# Known issues and future work


This section summarizes the current limitations of Sentimazon and possible future improvements. The project is functional as a notebook-based sentiment analysis pipeline, but there are still several areas that can be improved.

## What Is Missing or Limited

The main missing feature is real-time Amazon review scraping. The project was originally planned to collect live Amazon reviews using a scraper, but this part was postponed because of Amazon policy limitations and scraping restrictions. As a result, the current version uses a static Kaggle mobile review dataset instead of live review data.

The project is also limited because it is mainly implemented in a Jupyter Notebook. This is useful for experimentation and explanation, but it is less structured than a complete software application with separated Python modules, reusable functions, and a user interface.

Another limitation is that the dataset must be available locally and the file path must be correctly configured. If the dataset path is written as an absolute local path, the notebook may not run correctly on another computer.

## What Does Not Work as It Should

The current GitHub Actions CI workflow performs only basic validation. It checks that Python can be set up, dependencies can be installed, and the main files exist, but it does not yet execute the full notebook automatically.

The project also does not include a complete automated test suite. Preprocessing, aspect extraction, and sentiment analysis steps are tested mainly by running the notebook manually.

Transformer-based models such as DistilBERT and RoBERTa can take a long time to run, especially on a normal laptop without GPU acceleration. This may reduce usability for users with limited hardware resources.

The RoBERTa results also need further refinement and validation, because transformer models may require careful label handling and model-output interpretation depending on the selected pretrained model.

## Future Improvements

In the short term, the dataset loading process should be improved by using a relative path, such as:

```python
data = pd.read_csv("data/Mobile_Reviews_Sentiment.csv")
```

This would make the project easier to run on different computers.

The notebook could also be cleaned and reorganized into clearer sections, such as data loading, preprocessing, aspect extraction, model execution, evaluation, and visualization.

A useful improvement would be moving reusable functions into separate Python files. For example, text cleaning, aspect extraction, and model evaluation could be placed in separate modules instead of keeping everything inside the notebook.

## Testing and CI Improvements

The CI workflow could be improved by adding automated notebook execution. This would allow GitHub Actions to check whether `Main.ipynb` can run successfully from beginning to end.

Future CI improvements could include:

```text
Automated notebook execution
Unit tests for preprocessing functions
Unit tests for aspect extraction
Unit tests for evaluation metrics
Linting and formatting checks
Testing on multiple Python versions
```

A stronger CI pipeline would make the project more reliable and reduce the risk of errors when changes are added.

## Model Improvements

Future versions of Sentimazon could include more sentiment analysis models or improve the current comparison between VADER, DistilBERT, and RoBERTa.

Possible improvements include:

```text
Fine-tuning a transformer model on review data
Adding confusion matrices for model comparison
Adding per-aspect sentiment summaries
Improving neutral sentiment handling
Adding visualizations for model performance
```

The aspect extraction process could also be improved. Currently, the project focuses on selected aspects such as battery, price, quality, and performance. In the future, the system could automatically detect more product aspects from the dataset.

## Possible Product Expansion

In the long term, Sentimazon could be expanded from a notebook-based project into a small web application or dashboard.

Possible future features include:

```text
Upload a review dataset through a web interface
Select sentiment analysis models from the interface
Display aspect-based sentiment results visually
Generate automatic summary reports
Export results as CSV or PDF
Use a legal and stable external API for real-time review collection
```

This would make the project more accessible for non-technical users.

## Conclusion

The current version of Sentimazon provides a working sentiment analysis pipeline for mobile phone reviews. It includes text preprocessing, aspect extraction, multiple sentiment analysis methods, model evaluation, documentation, and a basic CI workflow.

However, the project still has limitations, especially the lack of real-time review scraping, limited automated testing, basic CI validation, and notebook-based structure. Future work should focus on improving reproducibility, automation, testing, model reliability, and possibly converting the project into a more user-friendly application.
````
