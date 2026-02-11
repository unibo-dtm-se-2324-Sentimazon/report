---
title: Development
has_children: false
nav_order: 5
---

# Development

The project is followed a data-centric and iterative strategy, focusing on reliability, modular desining, and reprouciablity. The first intention of the project was to implement an scraper to capture reviews from amazon website related to the target-product. However, the recent policies and limitations of amazon website regarding to data privacy protextion have hinder the project to achive its initaial goal.
Therefore, the publicly available amazon reviews from Kaggle website is used to not only consider the data from amazon website but also compliance with amazon data privacy and usage. The dataset cosnist of about 25400 reviews, mostly on English, as input of the project, providing adequate data for further computations. This transitions leads to development of relaiable NLP pipeline for processing and anlysing unstructured data to extract meanful insghts.

## Development strategy

The Sentimazon project is implemenined using Python ptograming language based on Jupyternotebook that enables excecution of each phase. Dependency management is handled and used in requtienmnet.txt file, highliting the requirnet libraries for ensure computational environment run efficiently.
The core libraries used in the sentimazon project is listed, as follow.
-   Pandas: manipulating structured and unstructured data
-   NLTK: Conducting pre-processing and processing the data for sentiment analysis
-   Matplotlib: Visualizing the results from aspect detection and sentiment analysis
-   Regular Expressions: cleaning the usntructural textual data to mitigate errors and noises

## Distributed Version Control System (DVCS)

The sentimazon project is used Git as its Distributed Version Control System. This helps the project to follow the class project guidline and create a history on what have done on the project until its finish. In addision, implementation of Git, as one of the most popular environment for developers, provides oppourtunity to share the project with bigger coumunity in order to improve the project efficncey in future. Since the project is procedeeded by one person, the program history is progressed on one and main branch, which includes stable version of the program. The development tree is tracked sequence of commits starting from load of data until result visualization. The commits give a vivid picture on project for developer of the project and other developers to see the changes and be able to improve the project efficiently.

## Commit Conventions

The project is used free-form messages in order to commit thoughat the changes without restricted structure. While the most of the project is followed the free-form commiting, the developer of the project relaizedd the cimmiting can be even more clearer if the convicetional commiting be use. Therefore, about midlle of the commits, the project is followed the following format for rest of the project. The project is followed the conventional commits specifications:
`<type>(<scope>): <short description>`
This form of cimmiting create a clear and traciable changes, providing a standardized format for commit messages. In this regards, it makes easier for developers to tract the history of the commits to understand the form of the commit and the changes related to it. Typical commit types including feat, fix, refactor, and docs as part of the format of commiting.

## Implementation

A list of sequential Natural language procrssing pipeline is created in order to initiate and process specific part of the the data manipulation for analysis. The project is inistate to excecute using the main notebook (Main.ipyb), which starting to lead the data and proceed the aspect based sentiment analysis. This initate prcosssing sequnces of phases that conduct part of compuations on the data based on the input dataset. Reading the stored data in a CSV file, including reviews from outside sources like Kaggle, is the responsibility of the first step, data acuaistion. To facilitate the normalization of the textual data and eliminate noise from subsequent analysis, the pre-processing step is carried out in the following step. After preprocessing, the sentiment associated with each aspect of sentiment is extracted using aspect-based sentiment analysis. Three categories—positive, negative, and neutral—are used to classify the sentiments. In order to display the sentiment distributions and aspect frequency, the visualization components are created as graphical charts in the last step.
