---
title: Deployment
has_children: false
nav_order: 8
---

# Deployment

## System Requirements
The softwares are required to be installed before the run the project in order to run the Sentimazon project, which are mentioned as follow.
* Pandas 2.0 or later
* Git
* Pip
* Visual studio Code with jupeter extension (or only jupter Notebook)

## User Installation
#### Step 1 – clone the repository
The repository of the project is published on the github and can be donwoloaded using the following command:
https://github.com/unibo-dtm-se-2324-Sentimazon/Sentimazon-Project.git
After downloading the project it can be navigate to the project using the following directory.
cd Sentimazon-Project
#### Step 2 – install dependencies related to the project
Install the libreries using the following cooment:
pip install -r requirements.txt
the requirements file consist of the following librarreis as the main dependencies used in the project. The libraries are listed as follow.
* Pandas 
* Numpy 
* Matplotlib 
* Nltk
* Scikit-learn
* Transformers
#### Step 3 – download required NLTK resources
The lexicon database related to the NLTK sentiment analyser model, VADER, is requires before procedding the codes. Hence, the gollowing command requies to run inside the python:
import nltk
nltk.download('vader_lexicon')
#### Step 4 – Run the Notebook
The project is developed on the visual studio code with jupeter extentions. However, the project also can be run on jupeter notebook. In either ways the project is written on the main.ipyb file cosniting the cells related to each step of the sentiment analysis.
Steps reqgarding to start and providng the results are listed as following steps:
1.	Lead the captured and visulazie the reviews dataset
2.	Apply procedures related to pre-processing including tokinaztiaion, lemmatization, stop-word removal and etc.
3.	Run the aspect extraction from amazon reviews
4.	Implement three sentiment analysis models including
* Vader
* DistilBert
* RoBERTa
5.	Evaluation and comparison of the models performance using the 4 metrics, as follow.
* Accuracy
* Precision
* Recall
* F1-score