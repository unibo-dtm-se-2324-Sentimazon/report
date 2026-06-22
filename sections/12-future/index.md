---
title: Future work
has_children: false
nav_order: 13
---

# Known Issues and Future Work

This section summarizes the current limitations of Sentimazon and possible future improvements. The project is functional as a sentiment analysis pipeline for mobile review data, and the revised version also includes a more structured repository, reusable modules, automated tests, CI validation, and a GitHub release. However, there are still several areas that can be improved in future versions.

## What Is Missing or Limited

The main missing feature is real-time Amazon review scraping. The project was originally planned to collect live Amazon reviews using a scraper, but this part was postponed because of Amazon policy limitations and scraping restrictions. As a result, the current version uses a static mobile review dataset instead of live review data.

The project is also still mainly executed through a Jupyter Notebook. In the revised version, the main logic has been moved into reusable Python modules under `src/sentimazon`, but the notebook is still the main execution interface. This is suitable for explanation and experimentation, but it is not yet a complete standalone application with a command-line interface, graphical interface, or web dashboard.

Another limitation is related to the dataset. The current version depends on a static CSV file stored inside the project `data` folder. This improves reproducibility, but it also means that the analysis is limited to the available dataset.

Transformer-based models such as DistilBERT and RoBERTa can also take a long time to run, especially on a normal laptop without GPU acceleration. This may reduce usability for users with limited hardware resources.

## What Does Not Work as It Should

The current version does not include real-time data collection. Therefore, the system cannot automatically collect new reviews from Amazon or another e-commerce platform.

The automated tests cover the main lightweight modules, including data loading, preprocessing, aspect extraction, and evaluation metrics. However, they do not cover every function in the project. In particular, transformer-based sentiment models are not included in the automated test suite because they require heavier dependencies and model downloads, which could make CI slower or less stable.

The RoBERTa and DistilBERT outputs may also require further refinement and validation. Transformer models can have different label formats depending on the selected pretrained model, so careful label handling is important when comparing them with the original dataset labels.

The project also does not yet include a complete user interface. Users need to run the notebook manually and follow the workflow step by step.

## Future Improvements

In the short term, more automated tests could be added. The current test suite is useful, but it could be extended to cover more edge cases and additional functions.

Possible testing improvements include:

```text
More unit tests for preprocessing functions
More unit tests for aspect extraction functions
Tests for label normalization
Tests for edge cases such as empty reviews
Tests for visualization function inputs
Automated notebook execution
```

The notebook could also be improved further by reducing the amount of direct logic inside notebook cells. The revised version already separates the main functions into modules, but future work could make the notebook even cleaner by keeping it mainly as a demonstration and execution layer.

A useful future improvement would be adding a command-line interface. This would allow users to run the pipeline without opening the notebook.

For example, a future command could be:

```text
python -m sentimazon --input data/Mobile_Reviews_Sentiment.csv --output results/
```

## Testing and CI Improvements

The CI workflow has already been improved compared with the first version. It now runs automated tests using `pytest` instead of only checking whether files exist.

Future CI improvements could include:

```text
Automated notebook execution
Linting and formatting checks
Testing on multiple Python versions
Testing on multiple operating systems
Optional test job for transformer-based models
Generating test reports
Measuring test coverage
```

A build matrix could also be added to test the project on different Python versions or operating systems. This would improve portability and make the workflow closer to a complete CI pipeline.

In the future, test coverage could also be measured using a tool such as `coverage.py`. This would make it easier to understand which parts of the code are already tested and which parts still need more validation.

## Model Improvements

Future versions of Sentimazon could include more sentiment analysis models or improve the current comparison between VADER, DistilBERT, and RoBERTa.

Possible model improvements include:

```text
Fine-tuning a transformer model on review data
Adding confusion matrices for model comparison
Improving neutral sentiment handling
Adding per-aspect sentiment summaries
Testing more pretrained sentiment models
Comparing runtime performance between models
```

The aspect extraction process could also be improved. Currently, the project focuses on selected product aspects such as battery, price, quality, and performance. In the future, the system could automatically detect more product aspects from the dataset instead of relying mainly on predefined keywords.

## Possible Product Expansion

In the long term, Sentimazon could be expanded from a notebook-based project into a small web application, dashboard, or command-line tool.

Possible future features include:

```text
Upload a review dataset through a web interface
Select sentiment analysis models from the interface
Display aspect-based sentiment results visually
Generate automatic summary reports
Export results as CSV or PDF
Use a legal and stable external API for real-time review collection
Add a command-line interface for non-notebook execution
```

This would make the project more accessible for non-technical users and easier to use outside an educational notebook environment.

## Conclusion

The current version of Sentimazon provides a working sentiment analysis pipeline for mobile phone reviews. It includes text preprocessing, aspect extraction, multiple sentiment analysis methods, model evaluation, visualizations, documentation, automated tests, CI validation, and a GitHub release.

Compared with the first version, the revised project is more structured and more aligned with Software Engineering practices. The code has been moved into reusable modules, tests have been added, CI has been improved, and the project was developed through a branch, pull request, merge, and release workflow.

However, the project still has limitations, especially the lack of real-time review collection, limited automated test coverage, notebook-based execution, and the runtime cost of transformer-based models. Future work should focus on improving automation, testing, model reliability, usability, and possibly converting the project into a more user-friendly application.