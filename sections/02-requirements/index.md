---
title: Requirements
has_children: false
nav_order: 3
---

# Requirements
- The user stories, functional, non-functional, and implementation requirements are defined and developed for the Sentimazon project. The project aims to analyses the reviews from Amazon databases using aspect bae sentiment analysis in order to discover meaningful insights. The collection, pre-process, analyze, and visualization of the results will assist business owners to have clear picture of customer’s expectation regarding to product(s).

## User stories
**Persona 1**: Data Analyst
Experts who have technical skills who do the data analysis on the customers online reviews.
-	As a data analyst, it requires to have access to dataset of online customer reviews, so I can do analysis on the reviews
-	As a data analyst, I want to apply the pre-processing steps in order to mitigate noises and errors, so I can have efficient model and accurate result.
-	As a data analyst, I want to do sentiment analysis on the cleaned textural data, so I can determine the positive, negative, and neutral aspects per review.
-	As a data analyst, I want to illustrate the final results and sentiment distributions, so I can present the output of project to technical and non-technical groups.

**Persona 2**: Business Decision Maker
Although both technical and non-technical stakeholders have interests to understand the customers reviews, the non-technical stakeholders are more interested on understanding customers expectations and views rather than coding part.
-	As a non-technical stakeholder, I want to have a vivid picture on aspects and sentiment related to each aspect of product, so I can understand the overall customer perception and satisfaction regarding to the product.
-	As a non-technical stakeholder, I want to see trends in reviews, so in that case I can determine the strengths and weakness of my product.


## Requirements analysis
\
The list of requrinemnts are explained the what the project should proceed. In this regard, functional, non-functional, and implemantion constrains as requirnments are separated and grouped. In addition, requrienmts have specific acceptance criteria as validation of the requrinment.
\
**2.1.Functional requrinments**

***2.1.1.Overview the textual data***
\
Requrinemnts:
The program must be able to capture and raed the reviews related to the products (ideally Amazon website)
\
Acceptance criteria:
-   the program is able to present various part of data including rating, row number, account name, and reviews
-   the textural data are saved on a accated file format (CSV) for next analysis.
\

***2.1.2.Pre-Processing***
\
Requrinemnts:
The program must be able to do pre-processing steps in order to mitigate further errors and noises in sentiment analysis
\
Acceptance criteria:
-   the program remove unnecceary charcters for the further analysis 
-   textual data is cleaned up and normalized
-   the each pre-processing step is stored in separate review column
\
***2.1.3.Sentiment Analysis***
\
Requrinemnts:
The program must be able to analyse the reviews and determine reviews sentiments respect to each aspect.
\
Acceptance criteria:
-   the sentiment anlayiss grouped each review intro thee category including positive, negative, and nutral sentiments
\
***2.1.4.Visualization***
\
Requrinemnts:
The program must be able to visualize  reviews and sentiment distribution
\
Acceptance criteria:
-   the program make bar-charts to visualize the sentimens related to each aspects.
-   The program displays the frquencey of each aspects and sentiments related to each review.
\
**2.2.Non-Functional requrinments**
\
***2.2.1.Usablity***
\
Requrinemnts:
The program should be easy to use by users with basic knowledge on data analysis.
\
Acceptance criteria:
-   Results and analysis presentation are labeled and understandable
-   Files and results are clearly orgonize
\
***2.2.2.Performance***
\
Requrinemnts:
The program must be able to process the data effictivly with high accuracy.
\
Acceptance criteria:
-   the program do the sentiment analysis within acceptable time period.
-   The program visualization and loading do not case significant delays on the process.
\
***2.2.3.Reliablity***
\
Requrinemnts:
The program must be able to provide the consistent outputs.
\
Acceptance criteria:
-   the program produce the same results and visulizations after re-running the program
-   Noises and errors are fixed during the analysis withoit leading to data corruption.
\
***2.2.4.Maintainablity***
\
Requrinemnts:
The program should be possible to modify with advanced models.
\
Acceptance criteria:
-   the program is structured in a way to be easy to mody and improve.
-   The program is modular and each part can be imrpve sepertally.

**2.3.Implemntation Requrinments**  
\
***2.3.1.Programing Language***
\
Requrinemnts:
The system should be programed using Python.
\
Justification:
Python csonsit of many useful librararies for various part of natural language processing, making it as most poupolar programming language for sentiment analysis.
\
Acceptance criteria:
-   The whole program is written using Python
\
***2.3.2.Data analysis and visualization***
\
Requrinemnts:
The program should implement required visualization libraries to present results.
\
Justification:
Impemnation of proper libraries leads to improve relaibality and efficiency of the analysis.
\
Acceptance criteria:
-   Loading and data manupilation is handle using the Pandas library
-   Visualization of the analysis is produced via python visualization related libraries.
\
3.	Glossary
-   Sentiment analysis: Sentiment analysis, also known as opinion mining, is a subfield of natural language processing (NLP) that identifies and extracts subjective information from textual data. The main goal of sentiment analysis is to determine the emotional tone behind a set of words, which helps in understanding the attitudes, opinions, and feelings expressed in the text.
-   Pre-processing: The process of converting raw data into a format that is readable and understandable by machines. To perform any related activity, the texts are first cleaned and pre-processed.
-   Visualization: Data visualization is the process of translating information into a visual format, such as a map or graph, in order to make it easier for the human brain to understand the data and extract insights from it. The main goal of data visualization is to make it easier to identify patterns, trends, and outliers in large data sets.
