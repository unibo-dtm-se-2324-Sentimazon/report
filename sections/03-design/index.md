---
title: Design
has_children: false
nav_order: 4
---

# Design

This section is presented the strategies applied to demonstrated requirements identified in the analysis. 

## Architecture 

The project, as a pipline-oriented analystics application, is implemented in python programing langage. The sentiamzon process the unstructured data by procceding steps in order to extract knowledge from the data. The arctecture of the Sentimazon consit of multipme components. The first step, data acuaistion, is responsible to read the stored data in CSV file including reviews from external resourceses such as Kaggle. The pre-processing step is perfromed in the next step in order to proucede the normalization of the textual data and remove noises from the further analysis. Following the preprocessing, the aspect based sentiment analysis is applied to extract the sentiment related to each aspect of sentiment. The sentiments are classified into three categories inclusing positive, negative, and neutral. At the final step, the visualization components is generated the graphical charts in otder to present the sentiments distributions and aspect frequency. The architecture is perfocmed and structured using python programming language, which is presenteded as follow.

![Activity diagram](./imgs/Architecture.png)

## Modelling
The modelling section is designed based on the some core domain entities of Sentimazon including:
•	Review
•	Aspects of products
•	Sentiment
•	Dataset
•	Analyst
•	Results visualization
The Class Model is designed using the entities and their relationships. The model is presented, as follow.
![Architecture](./imgs/Architecture.jpg)


### Domain driven design (DDD) modelling

- Which are the bounded contexts of your domain? 
- Which are domain concepts (entities, value objects, aggregates, etc.) for each context?
- Are there repositories, services, or factories for each/any domain concept?
- What are the relavant domain events in each context?

> Context map diagrams are welcome here

### Object-oriented modelling

- What are the main data types (e.g. classes) of the system?
- What are the main attributes and methods of each data type?
- How do data types relate to each other?

> UML class diagrams are welcome here

### In case of a distributed system

- How do the domain concepts map to the architectural or infrastuctural components?
    + i.e. which architectural/component is responsible for which domain concept?
    + are there data types which are required onto multiple components? (e.g. messages being exchanged between components)

- What are the domain concepts or data types which represent the state of the distributed system?
    + e.g. state of a video game on central server, while inputs/representations on clients
    + e.g. where to store messages in an instant-messaging app? for how long?

- Are there domain concepts or data types which represent messages being exchanged between components?
    + e.g. messages between clients and servers, messages between servers, messages between clients

## Interaction

- How do components *communicate*? *When*? *What*?

- Which **interaction patterns** do they enact?

> UML sequence diagrams are welcome here

## Behaviour

- How does **each** component *behave* individually (e.g., in *response* to *events* or messages)?
    + Some components may be *stateful*, others *stateless*

- Which components are in charge of updating the **state** of the system? *When*? *How*?

> UML state diagrams or activity diagrams are welcome here

## Data-related aspects (in case persistent storage is needed)

- Is there any data that needs to be stored?
    - *What* data? *Where*? *Why*?

- How should **persistent data** be **stored**? Why?
    - e.g., relations, documents, key-value, graph, etc.

- Which components perform queries on the database?
    - *When*? *Which* queries? *Why*?
    - Concurrent read? Concurrent write? Why?

- Is there any data that needs to be shared between components?
    - *Why*? *What* data?

