---
typora-copy-images-to: ./attachments
Tags: IBM
---

# Data Science Methodology

[toc]

![image-20230620224220808](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230620_1687297367.png)

## Introduction to CRISP - DM

## From Problem to Approach

### Business Understanding

### Analytics Approach



## From Requirements to collections

### Data Requirements

1. Select the cohort
2. Define the data

### Data Collection

1. Gathering available data
2. Defer inaccessible data
3. Merge data

## From Understanding to Preparation

### Data Understanding

1. **Descriptive statistics**
   1. Univariate statistics: mean, medium, maximum, minimum, standard deviation
   2. Pairwise correlations: How closely certain variables were related
   3. Histogram: The histograms would help them decide how to consolidate those values.
2. **Look at data quality**
   1. Missing values
   2. Invalid or mislead values
3. **Iterative Process**
   - Iterative data collection and understanding

### Data Preparation

1. **Cleansing data**
   1. Addressing the invalid values
   2. Remove the duplicates
2. **Transforming data**
3. **Feature Engineering**: Using domain knowledge to create the features for making the machine algorithms work
4. **Text Analysis**: The text analysis is critical to ensure that the proper groupings are set, and that the programming is not overlooking what is hidden within.

## From Modeling to Evaluation

### Modeling

1. descriptive model
2. Predictive model - yes/no or stop/go outcomes

### Evaluation

**Evaluation answers the question:**

- Does the model used really answer the initial question or does it need to be adjusted?

**Two phases for modeling evaluation:**

1. **Diagnostic measures**: which is used to ensure the model is working as intended
2. **Statistical significance**



#### How to determine which model is the optimal

**Using the ROC curve:**

Diagnostic tool for classification model evaluation:

1. **Classification model performance**: This cureve quantifies how well a **binary classification** model performs, declassifying the yes and no outcomes when some discrimination criterion is varied.
2. True-Positive Rate vs False-Positive Rate:
3. Optimal model at maximum separation

## From Deployment to Feedback

### Deployment

### Feedback

**Assessing model performance:**

1. **Define review process:**
   1. To measure results of applying the risk model to the CHF patient population
   2. Track patients who recieved intervention
   3. Meansure effectiveness of intervention

2. **Refinement: Refine model**
   1. Initial review after the first year of implementation
   2. Based on feedback data and knowledge gained
   3. Participation in intervention program
   4. Possibly incorporate detailed pharmaceutical data originally deferred
   5. Other possible refinements as yet known

3. **Redeployment**:
   - Continue modeling, deployment, feedback, and refinement throughout the life of the intervention program.



