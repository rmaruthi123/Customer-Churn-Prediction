# Customer Churn Prediction

A Machine Learning project that predicts whether a telecom customer is likely to churn based on customer demographics, services, contract details, and billing information.

## Live Demo

[Customer Churn Prediction App](https://customer-churn-prediction-knocp4dhsdcvtmynb5hsko.streamlit.app/)

## Project Overview

Customer churn is an important business problem for telecom companies. This project uses Machine Learning to identify customers who are likely to leave the service.

The project includes data preprocessing, exploratory data analysis, feature encoding, model training, model comparison, feature importance analysis, and deployment using Streamlit.

## Dataset

The project uses the Telco Customer Churn dataset.

- Number of records: 7,043
- Original features: 20
- Target variable: `Churn`

The target variable contains:

- `Yes` → Customer churned
- `No` → Customer did not churn

## Data Preprocessing

The following preprocessing steps were performed:

- Checked for missing values
- Converted `TotalCharges` from object to numeric
- Replaced missing `TotalCharges` values with `0`
- Removed `customerID`
- Converted categorical variables using One-Hot Encoding
- Converted `Churn` into binary values
- Split the dataset into training and testing sets
- Applied StandardScaler for Logistic Regression

## Exploratory Data Analysis

EDA was performed to understand:

- Customer demographics
- Tenure distribution
- Monthly and total charges
- Contract types
- Internet services
- Payment methods
- Churn distribution

## Machine Learning Models

Three classification models were trained and compared:

1. Logistic Regression
2. Decision Tree
3. Random Forest

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score

## Model Comparison

| Model | Accuracy | Precision | Recall | F1 Score |
|---|---:|---:|---:|---:|
| Logistic Regression | 78.42% | 72.15% | 30.48% | 42.86% |
| Decision Tree | 79.42% | 63.13% | 54.01% | 58.21% |
| Random Forest | 80.06% | 67.68% | 47.59% | 55.89% |

### Final Model

The **Decision Tree** was selected as the final model based on the highest F1 Score and better recall for the churn class.

- Accuracy: **79.42%**
- Recall: **54.01%**
- F1 Score: **58.21%**

Recall and F1 Score were considered important because correctly identifying customers who may churn is an important objective of the project.

## Feature Importance

Feature importance from the Decision Tree showed that the following features had a strong influence on the model's predictions:

- Tenure
- Fiber Optic Internet Service
- Electronic Check Payment Method
- Total Charges
- Monthly Charges
- Multiple Lines
- Internet Service
- Contract
- Tech Support

`tenure` was the most important feature in the trained Decision Tree model.

> Feature importance indicates how much a feature contributes to model predictions. It does not imply that the feature directly causes customer churn.

## Streamlit Application

The trained model was deployed using Streamlit.

Users can enter customer information such as:

- Gender
- Senior Citizen status
- Tenure
- Internet Service
- Contract
- Payment Method
- Monthly Charges
- Total Charges
- Technical Support
- Online Security
- Streaming Services

The application returns:

- Churn / No Churn prediction
- Predicted churn probability

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
- Streamlit
- Git & GitHub

## Project Structure

```text
Customer-Churn-Prediction/
│
├── app.py
├── churn_model.pkl
├── feature_names.pkl
├── requirements.txt
└── README.md