# Customer Churn Prediction (Telecom) - Graduation Project

## Project Overview

This is a graduation project focused on building a machine learning model to predict customer churn for a telecom company.

The project covers the full analytical pipeline:

- Data loading and joining multiple tables
- Data preprocessing and feature engineering
- Exploratory Data Analysis (EDA)
- Correlation analysis (phik)
- Model training and comparison
- Hyperparameter tuning
- Model evaluation and threshold optimization
- Business interpretation of results

The goal is not only to build a predictive model, but also to identify key churn drivers and provide actionable insights for customer retention.

---

## Problem Context

Customer churn is a critical business problem in the telecom industry. Identifying customers at risk of leaving allows companies to take proactive actions and reduce revenue loss.

The objective of this project is to develop a binary classification model that predicts whether a customer is likely to churn based on contract, service usage, and demographic data.

---

## Dataset Description

The dataset consists of multiple relational tables:

- **contract** - contract details and billing information
- **personal** - customer demographic data
- **internet** - internet services and add-ons
- **phone** - phone service information

These tables are joined using `customer_id` to form a unified dataset.

**Important:**
The dataset is not included in this repository due to usage restrictions.

---

## Data Processing & EDA

The following steps were performed:

- Data cleaning and standardization (snake_case, data types correction)
- Handling missing values based on business logic
- Feature engineering:
  - customer tenure (`contract_duration_days`)
  - number of subscribed services (`num_services`)
- Analysis of categorical and numerical features
- Correlation analysis using **phik**
- Identification of key patterns related to churn

---

## Modeling Approach

### Models Used

- **DummyClassifier** (baseline)
- **RandomForest**
- **MLP (Neural Network)**
- **CatBoost**

### Evaluation Strategy

- Stratified train-test split (75/25)
- Cross-validation using StratifiedKFold
- Main metric: ROC-AUC
- Additional metrics: precision, recall, F1-score, confusion matrix

### Results

- Baseline model (DummyClassifier) achieved ROC-AUC = 0.50  
- Best model: **CatBoost**
  - ROC-AUC = 0.91 (cross-validation)
  - ROC-AUC = 0.93 (test set)

### Threshold Optimization

- Optimal classification threshold: 0.30
- Improved recall for churn detection with acceptable precision trade-off

---

## Key Findings

- The most important factor is **customer tenure**
- Medium-tenure customers (around **2.5-4 years**) show the highest churn risk

---

## Business Recommendations

- Focus retention efforts on medium-tenure customers
- Introduce flexible pricing and bundled offers
- Encourage long-term contracts
- Use the model for regular customer risk scoring
- Integrate predictions into CRM workflows for proactive intervention

---

## Project Structure

```
telecom_customer_churn_prediction/

├── telecom_customer_churn_prediction.ipynb
├── README.md
└── .gitignore
```

---

## Tech Stack

- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- CatBoost
- phik

---

## Author

Tatiana Pletneva Chavand
Data Science & Machine Learning

**Keywords:** Machine Learning, Classification, Churn Prediction, Telecom, CatBoost, EDA
