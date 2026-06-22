---
title: Validation
has_children: false
nav_order: 6
---

# Validation

## Testing approach

The validation of Sentimazon was performed using a combination of automated and manual testing. The main goal of the testing activity was to check that the core parts of the sentiment analysis workflow work correctly after the project was refactored from a notebook-based implementation into a modular Python project.

The project did not follow a strict Test-Driven Development approach. The first version of the project was implemented mainly inside a Jupyter Notebook. After the project revision, the logic was moved into reusable Python modules, and automated tests were added to validate the main lightweight components.

The testing framework used in the project is `pytest`. It was selected because it is simple to use, works well with Python projects, and can be easily integrated into GitHub Actions for Continuous Integration.

The automated tests focus on the following parts of the project:

- Data loading
- Text preprocessing
- Aspect extraction
- Evaluation metrics

Transformer-based models such as DistilBERT and RoBERTa were not included in the automated tests because they require heavier dependencies and model downloads. Including them in the automated test suite could make the tests slower and less stable in the CI environment.

## Testing (automated)

The automated tests were implemented using `pytest` and placed inside the `tests` folder. The tests were designed to check the main functions of the project after the refactoring process.

The tests are connected to the main project requirements as follows:

| Requirement | Related test file | Purpose |
|---|---|---|
| Load and prepare review data | `test_data_loader.py` | Checks that the required dataset columns are selected correctly |
| Preprocess textual review data | `test_preprocessing.py` | Checks text cleaning and creation of the cleaned text column |
| Extract product-related aspects | `test_aspect_extraction.py` | Checks that noun extraction works correctly |
| Evaluate sentiment model outputs | `test_evaluation.py` | Checks that evaluation metrics return valid values |

The current automated test result is:

```text
7 passed