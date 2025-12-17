# Customer-Churn-Phase-3
Customer analytics and prediction project

## Project Overview

This project focuses on predicting customer churn for a telecommunications company (SyriaTel) using supervised machine learning. Customer churn occurs when a customer stops doing business with the company, resulting in lost revenue and increased costs associated with acquiring new customers. The goal of this project is to build and evaluate classification models that can identify customers who are likely to churn, enabling the business to take proactive retention actions.

This project was completed as part of **Phase 3: Machine Learning Fundamentals**, with an emphasis on classification, model evaluation, and business-driven decision making.

---

## Business Problem

Customer retention is a critical challenge in the telecommunications industry. Retaining existing customers is significantly more cost-effective than acquiring new ones. When customers churn, the company loses future recurring revenue and must invest additional resources in marketing and onboarding replacements.

The key business question addressed in this project is:

> **Can we predict which customers are likely to churn so that SyriaTel can intervene early and reduce customer attrition?**

Since churn is a binary outcome (churn vs. no churn), this is framed as a **binary classification problem**. Recall is prioritized as the primary evaluation metric because failing to identify customers who will churn has a higher business cost than incorrectly flagging a loyal customer.

---

## Data Understanding

The dataset contains customer-level information related to service usage, subscription plans, and customer service interactions. Each row represents one customer, and the target variable `churn` indicates whether the customer left the company.

**Key characteristics:**

* 3,333 customer records
* 21 features including numerical and categorical variables
* Class imbalance: approximately **14.5% churners** and **85.5% non-churners**

This imbalance makes metrics such as recall, confusion matrices, and ROC-AUC particularly important when evaluating model performance.

---

## Data Preparation

The following preprocessing steps were applied:

* Removed non-predictive identifiers (e.g., phone number)
* Separated features from the target variable to avoid data leakage
* One-hot encoded categorical variables
* Split the data into training and test sets using stratified sampling
* Applied feature scaling for models sensitive to feature magnitude (logistic regression)

These steps ensured that models were trained on clean, appropriately formatted data and evaluated on unseen observations.

---

## Modeling Approach

Three models were evaluated:

### 1. Baseline Logistic Regression

Logistic regression was used as the baseline model due to its simplicity and interpretability. It provides a clear benchmark for comparison and helps identify whether more complex models are necessary.

**Strengths:**

* Easy to interpret
* Fast to train

**Limitations:**

* Struggles to capture non-linear relationships
* Low recall for churners in this dataset

### 2. Baseline Decision Tree

A baseline decision tree was trained to capture non-linear patterns in customer behavior.

**Strengths:**

* Handles non-linear relationships
* More flexible than logistic regression

### 3. Tuned Decision Tree (Final Model)

A decision tree with controlled depth and minimum samples per split was used to reduce overfitting and improve generalization.

This model demonstrated the best balance between recall and overall performance, making it the most suitable choice for identifying high-risk churn customers.

---

## Model Evaluation

Models were evaluated using:

* **Recall** (primary metric)
* **Confusion Matrix**
* **Classification Report**
* **ROC-AUC Score**

Recall was emphasized because the business impact of missing a churner is higher than incorrectly flagging a non-churner.

The tuned decision tree achieved the highest recall, significantly outperforming logistic regression in identifying customers who were likely to churn.

---

## Final Model Selection

The **tuned decision tree classifier** was selected as the final model due to its superior recall and ability to capture non-linear relationships in the data. While it is less interpretable than logistic regression, its improved performance makes it more effective for proactive churn prevention strategies.

---

## Business Recommendations

Based on the model results, SyriaTel should:

* Prioritize retention efforts for customers flagged as high risk
* Proactively engage customers with frequent customer service calls
* Review pricing or service plans for customers with high usage charges
* Use the model as an early warning system to guide targeted outreach

Implementing these actions can help reduce churn and improve long-term customer value.

---

## Limitations

* The model relies only on historical usage and service data
* External factors such as competitor pricing and customer sentiment are not included
* Class imbalance may still affect prediction reliability

Predictions should be used as decision support, not as absolute outcomes.

---

## Next Steps

Future work could include:

* Incorporating additional customer data (tenure, billing history, satisfaction scores)
* Exploring ensemble models for improved performance
* Monitoring model performance over time as customer behavior changes

---

## Repository Structure

```
├── data/
│   └── SyriaTel Customer Churn.csv
├── notebooks/
│   └── churn_prediction.ipynb
├── README.md
```

---

## Tools & Libraries

* Python
* pandas, numpy
* scikit-learn
* matplotlib

---

## Author

**Doris Mawia Mutie**
Data Science Student | Finance & Analytics Background
