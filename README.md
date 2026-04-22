# Predicting Adults' Stroke Risk Using Support Vector Machines

A machine learning project that uses **Support Vector Machines (SVMs)** to predict adult stroke risk from demographic and health behavior data.

## Overview

This study uses **Support Vector Machines** to predict stroke risk based on demographics and health behaviors. The project uses data from the **2022 National Health Interview Survey (NHIS)** with **48 variables** on age, sex, sleep patterns, alcohol and cigarette use, and physical activity from over **35,000 adults**.

Three SVM models were tested:

- **Linear SVM**
- **Polynomial SVM**
- **Radial SVM**

The goal was to compare model performance and identify the most important predictors of stroke risk.

## Introduction

Stroke risk is influenced by a combination of demographic, behavioral, and lifestyle factors. In this project, SVMs were used to model these relationships and assess how well different kernel types could classify stroke and non-stroke cases.

This analysis also highlights the challenge of predicting health outcomes in imbalanced datasets, where positive stroke cases are much less common than non-stroke cases.

## Technical Background

**Support Vector Classifiers** find an optimal hyperplane that maximizes the margin between two classes. The margin is the distance between the decision boundary and the nearest points.

**Kernels** allow SVMs to model different types of decision boundaries:

- **Linear**: best for simpler relationships
- **Polynomial**: captures curved decision boundaries
- **Radial (RBF)**: handles more complex nonlinear patterns

### Advantages

- Handles nonlinear patterns well
- Works effectively in high-dimensional data
- Can be tuned for strong classification performance

### Disadvantages

- Slower training
- Sensitive to noise
- Requires careful hyperparameter tuning

## Dataset

The dataset came from the **2022 National Health Interview Survey (NHIS)**.

- Over **35,000 adult observations**
- **48 predictor variables**
- Includes demographic and health-related features such as:
  - age
  - sex
  - sleep habits
  - hours worked
  - alcohol consumption
  - cigarette use
  - physical activity

## Methodology

### Data Cleaning

The data was cleaned by:

- Converting coded missing values to `NA`
- Dropping variables with high missingness
- Converting categorical variables to factors
- Scaling continuous variables for consistency

### Train-Test Split

- **70%** of the data was used for training
- **30%** of the data was used for testing

### Class Imbalance

Because stroke cases were less frequent, **class weights** were applied during model training to give more importance to positive stroke cases.

### Model Implementation

Three SVM models were trained:

- **Linear SVM**
- **Polynomial SVM**
- **Radial SVM**

### Hyperparameter Tuning

Best models were selected based on validation accuracy after tuning:

- **Linear SVM**: cost
- **Polynomial SVM**: cost, degree, and coefficient
- **Radial SVM**: cost and gamma

### Model Evaluation

Models were evaluated using:

- **Accuracy**
- **Precision**
- **Recall**
- **F1-score**
- **Confusion matrix**

## Results

The SVM models produced similar overall performance, with accuracy around **0.70 to 0.73**.

### Model Metrics

| Model | Accuracy | Precision | Recall | F1-Score |
|------|---------:|----------:|-------:|---------:|
| Linear SVM | 0.700 | 0.051 | 0.718 | 0.096 |
| Radial SVM | 0.709 | 0.052 | 0.710 | 0.097 |
| Polynomial SVM | 0.727 | 0.055 | 0.710 | 0.103 |

### Key Findings

- The **linear SVM** achieved the highest recall but had low precision, resulting in many false positives
- The **polynomial SVM** had the highest overall accuracy in the summary table
- Overall, all models struggled to clearly separate stroke and non-stroke cases
- Performance suggests that stroke prediction is a complex classification problem

## Important Predictors

According to the linear SVM variable importance results, the strongest predictors included:

- **Hours Worked**
- **Hours of Sleep**
- **Alcohol Consumption Days Per Year**
- **Age**
- **BMI**
- **Duration of moderate activity**
- **Duration of vigorous activity**
- **Cigarettes consumed per month**

The discussion also emphasized:

- **Age**
- **Hours Worked**
- **Hours of Sleep**

as especially important predictors of stroke risk.

## Discussion

The findings suggest that demographic and lifestyle features such as **age**, **hours worked**, and **hours of sleep** are strongly associated with stroke risk. However, the decision boundary visualizations showed substantial overlap between stroke and non-stroke cases, which made classification difficult.

Although SVMs were useful for exploring patterns in the data, the models had limited precision in identifying stroke cases.

## Conclusion

This project showed that **Support Vector Machines** can be used to study adult stroke risk using survey-based health data. While the models achieved moderate accuracy, they struggled to identify positive stroke cases with high precision.

The results suggest that stroke risk prediction may benefit from:

- improved feature engineering
- more balanced data strategies
- additional clinical or behavioral variables
- further model tuning and comparison with other machine learning methods

## Tools

- **Language:** R
- **Environment:** RStudio
- **Methods:** Linear SVM, Polynomial SVM, Radial SVM

## Applications

This type of modeling can support work in:

- disease prediction
- medical diagnostics
- geospatial analysis
- face recognition

## Acknowledgments

- **2022 National Health Interview Survey (NHIS)**
- **IPUMS Health Surveys**
