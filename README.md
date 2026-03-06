# Credit Card Customer Churn Prediction

A machine learning project that predicts whether a credit card customer is likely to churn (leave the service) using behavioral and demographic data. The project applies data analysis, feature engineering, and a K-Nearest Neighbors (KNN) classification model to identify at-risk customers and support proactive retention strategies.

## Overview

Customer churn is a major challenge in the financial services industry. Losing customers impacts revenue, increases acquisition costs, and reduces long-term business stability.

This project builds a predictive model that analyzes customer attributes and credit card usage patterns to estimate the probability of churn. The goal is to help organizations identify customers who may discontinue their credit card services and take preventive action.

## Dataset

The dataset contains information about credit card customers including demographic attributes, account details, and transaction behavior.

### Dataset Characteristics

- **Number of records:** 10,127
- **Number of features:** 23
- **Target variable:** `Attrition_Flag`

### Important Features

- Customer_Age
- Gender
- Education_Level
- Marital_Status
- Income_Category
- Card_Category
- Months_on_book
- Total_Relationship_Count
- Months_Inactive_12_mon
- Contacts_Count_12_mon
- Credit_Limit
- Total_Revolving_Bal
- Avg_Open_To_Buy
- Total_Trans_Amt
- Total_Trans_Ct
- Avg_Utilization_Ratio

Target Label:

- **0 → Existing Customer**
- **1 → Attrited Customer**

## Project Workflow

The project follows a typical machine learning pipeline:

### 1. Data Understanding
- Explored dataset structure and statistics
- Identified feature relationships using visualizations
- Observed patterns in credit card usage and churn behavior

### 2. Data Preparation
- Handled missing categorical values
- Converted target variable to binary format
- Encoded categorical variables
- Feature selection and transformation
- Train-test split (70% training / 30% testing)

### 3. Exploratory Data Analysis
Key insights discovered:

- Customers with **higher transaction activity are less likely to churn**
- **Inactive customers** show higher churn probability
- **Utilization ratio near zero** indicates low engagement with the card
- Strong correlation between:
  - `Total_Trans_Amt` and `Total_Trans_Ct`
  - `Credit_Limit` and `Avg_Open_To_Buy`

### 4. Model Selection

Several algorithms were evaluated:

- Linear / Polynomial Regression
- Decision Trees
- K-Nearest Neighbors (KNN)

**KNN was selected** due to:

- Ability to model non-linear relationships
- Good performance with mixed data types
- No strong assumptions about data distribution
- Suitable for moderate-sized datasets

### 5. Model Training

The optimal value of **k = 7** was selected using hyperparameter tuning.

Model pipeline:

1. Data preprocessing
2. Feature scaling
3. Train-test split
4. Hyperparameter tuning
5. KNN model training
6. Performance evaluation

## Model Performance

### Accuracy
Accuracy: 87.2%


### Confusion Matrix

| Metric | Value |
|------|------|
| True Positives | 147 |
| False Positives | 40 |
| True Negatives | 2503 |
| False Negatives | 349 |

### Classification Metrics

| Metric | Score |
|------|------|
| Precision | 0.86 |
| Recall | 0.87 |
| F1 Score | 0.85 |

### Class-wise Performance

**Existing Customers (Class 0)**  
- Precision: 0.88  
- Recall: 0.98  
- F1 Score: 0.93  

**Churned Customers (Class 1)**  
- Precision: 0.79  
- Recall: 0.30  
- F1 Score: 0.43  

## Key Insights

- Customer activity is a strong indicator of retention.
- Transaction count and transaction amount are strongly correlated with churn probability.
- Inactive users show higher churn risk.
- Model performs well for identifying active customers but requires improvement for detecting churned customers.

## Deployment Considerations

To maintain model effectiveness in real-world environments:

### Periodic Retraining
- Retrain with updated data regularly
- Detect concept drift

### Threshold Optimization
Adjust classification thresholds depending on business priorities.

### Model Monitoring
Track key metrics such as:

- Accuracy
- Recall for churned customers
- F1-score
- ROC-AUC

### A/B Testing
Compare model performance with alternative models such as logistic regression or ensemble models.

## Potential Improvements

Future enhancements may include:

- Addressing class imbalance more effectively
- Applying ensemble models such as Random Forest or Gradient Boosting
- Feature engineering with behavioral metrics
- Hyperparameter optimization
- Model explainability using SHAP or LIME

## Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

## Project Structure

```
Credit-Card-Churn-Prediction/
│
├── BasicDataAnalysis.ipynb
├── DetailedDataAnalysis.ipynb
├── CorelationGraphs.ipynb
├── Model.ipynb
└── README.md
```

## Applications

- Banking customer retention systems
- Credit risk analytics
- Customer behavior analysis
- Financial services churn prediction