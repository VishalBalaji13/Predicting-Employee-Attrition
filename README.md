# Predicting-Employee-Attrition

This repository contains the implementation of a machine learning project aimed at predicting employee attrition. 

## Project Overview

### 1. Stakeholder
The primary stakeholder for this project is the Human Resources (HR) department of a mid-to-large-sized organization. They are concerned about the costs associated with employee turnover and require a proactive solution to identify employees who are at risk of leaving the company.

### 2. Problem Statement
Employee attrition represents a significant cost for businesses due to recruitment expenses, training investments, and lost productivity. The HR department requires a predictive model that accurately identifies employees at risk of leaving, enabling them to implement proactive retention strategies.

### 3. Dataset
The project utilizes the "IBM HR Analytics Employee Attrition & Performance" dataset, which is publicly available on Kaggle. 
The dataset contains 35 attributes encompassing employee demographics, job roles, and various satisfaction metrics.

## Methodology

### 4. Models Used and Rationale
We experimented with two distinct types of machine learning models, each tuned with three different hyperparameter settings:

*   **Random Forest Classifier:** Chosen for its robustness, its ability to provide feature importance analysis, and its capacity to handle both categorical and numerical data effectively.
    *   *Hyperparameter tuning:* Number of trees (100, 200, 500)
*   **Logistic Regression:** Chosen to serve as a strong baseline model due to its high interpretability and efficiency in handling binary classification tasks.
    *   *Hyperparameter tuning:* Regularization parameter C (0.01, 1, 10)

### 5. Feature Selection & Engineering
Feature selection was driven by exploratory data analysis (EDA) and domain knowledge. 
*   **Existing Features Selected:** Age, JobSatisfaction, YearsAtCompany, WorkLifeBalance, BusinessTravel, and TotalWorkingYears.
*   **Engineered Features:**
    *   `JobTenure` = `YearsAtCompany / (TotalWorkingYears + 1)` (Created to normalize tenure).
    *   `Satisfaction_Score` = `(JobSatisfaction + WorkLifeBalance) / 2` (Created to provide a comprehensive overall satisfaction metric).

## Results and Evaluation

### 6. Model Evaluation
The performance of the models was evaluated using the following metrics:
*   **Accuracy:** To measure the overall correctness of the model.
*   **Precision:** Crucial to minimize false positives when predicting attrition.
*   **Recall:** Crucial to ensure that employees who are genuinely likely to leave are successfully identified.
*   **F1-Score:** Used to provide a balanced metric between precision and recall.

### 7. Recommendation
Based on the analysis, the Random Forest model with optimized hyperparameters performed best in balancing the evaluation metrics. It is recommended for deployment, pending further validation in real-world HR scenarios.

## Future Work
*   Incorporate additional external factors, such as market conditions or detailed employee feedback surveys.
*   Test more advanced modeling techniques, such as Gradient Boosting machines or Neural Networks.
*   Refine feature selection and improve model interpretability using SHAP (SHapley Additive exPlanations) values.
