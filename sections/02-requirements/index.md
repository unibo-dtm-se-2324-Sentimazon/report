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

- The requirements must explain **what** (not how) the software being produced should do.
    - You should not focus on the particular problems, but exclusively on what you want the application to do.
- Requirements must be clearly identified, and possibly numbered.
- Requirements are divided into:
    - **Functional**: some functionality the software should provide to the user.
    - **Non-functional**: requirements that do not directly concern behavioral aspects, such as consistency, availability, security, efficiency, etc.
    - **Implementation**: constrain the entire phase of system realization, for instance by requiring the use of a specific programming language and/or a specific software dependency.
        - These constraints should be adequately justified by political / economic / administrative reasons (which must be written down)...
        - ...otherwise, implementation choices should emerge *as a consequence of* design (and therefore described in the design section).
- If there are domain-specific terms, these should be explained in a **glossary**.
- Each requirement must have its own **acceptance criteria**.
    - These will be important for the validation phase. 

> You may consider adding a use-case diagram here (via PlantUML) to better visualize the requirements and their relationships