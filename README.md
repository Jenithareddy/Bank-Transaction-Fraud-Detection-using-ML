# Bank Transaction Fraud Detection Using Machine Learning

## Project Overview

Financial fraud continues to be one of the biggest challenges for banks and financial institutions, resulting in billions of dollars in losses every year. Traditional rule-based fraud detection systems struggle to keep up with rapidly evolving fraud patterns, leading to both missed fraudulent transactions and unnecessary false alerts.

This project develops an end-to-end Machine Learning solution for detecting fraudulent bank transactions by combining **unsupervised anomaly detection** with **supervised classification**. Using the Kaggle Bank Transaction Dataset, the project identifies suspicious transaction behavior, engineers meaningful features, builds predictive models, and generates actionable business insights that can be integrated into real-world banking systems.

## Objectives

* Detect fraudulent bank transactions using Machine Learning.
* Discover hidden fraud patterns through Exploratory Data Analysis (EDA).
* Engineer behavioral, temporal, and financial features that improve fraud detection.
* Identify anomalous transactions using Isolation Forest.
* Train a Random Forest classifier to predict fraudulent transactions.
* Minimize false positives while maximizing fraud detection accuracy.
* Generate business recommendations for financial institutions.

## Dataset

**Source:** Kaggle – Bank Transaction Dataset

### Dataset Statistics

* **Total Transactions:** 2,512
* **Missing Values:** None
* **Duplicate Records:** None

### Features Include

* Transaction Amount
* Transaction Type
* Timestamp
* Device ID
* Browser
* IP Address
* Customer Age
* Account Balance
* Login Attempts
* Geographic Information

## Tech Stack

### Programming Language

* Python

### Data Analysis

* Pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn
* Isolation Forest
* Random Forest Classifier
* GridSearchCV

### Development Environment

* Jupyter Notebook

---

## Project Workflow

### 1. Data Exploration

Performed exploratory data analysis to understand transaction behavior, customer characteristics, and fraud-related patterns.

Key analyses included:

* Transaction amount distribution
* Customer age distribution
* Account balance analysis
* Transaction type frequency
* Time-based transaction patterns
* Category-wise transaction behavior

### 2. Feature Engineering

Created new features to improve model performance.

Examples include:

* Transaction Hour
* Transaction Day
* Weekday vs Weekend
* Time Since Last Transaction
* Transaction Frequency
* Login-to-Transaction Time
* Amount-to-Balance Ratio
* Historical Spending Deviation
* Average Transaction Comparison

Categorical variables were encoded using One-Hot Encoding before model training.

### 3. Anomaly Detection

Implemented the **Isolation Forest** algorithm to identify suspicious transactions without requiring labeled fraud data.

The model:

* Learned normal transaction behavior
* Identified approximately **5%** of transactions as anomalies
* Flagged **126 suspicious transactions** for further analysis

### 4. Fraud Classification

The anomaly labels generated from Isolation Forest were used to train a **Random Forest Classifier**.

Dataset split:

* Training: 80%
* Testing: 20%

The classifier learned fraud patterns using engineered behavioral and financial features.

### 5. Hyperparameter Optimization

Improved model robustness using **GridSearchCV** with 5-fold cross-validation.

Optimized parameters included:

* Number of Trees (`n_estimators`)
* Maximum Tree Depth (`max_depth`)
* Feature Selection Strategy (`max_features`)

## Results

### Model Performance

| Metric    | Value    |
| --------- | -------- |
| Accuracy  | **97%**  |
| Precision | **0.81** |
| Recall    | **0.52** |
| F1 Score  | **0.63** |

The tuned Random Forest model achieved high prediction accuracy while maintaining strong precision for identifying fraudulent transactions.

## Key Insights

The analysis revealed several important fraud indicators:

* Large transaction amounts relative to account balance
* Multiple failed login attempts before successful transactions
* Unusual transaction timing
* Extremely short intervals between consecutive transactions
* Transactions originating from unfamiliar locations or devices
* Significant deviation from historical customer spending patterns

These indicators can be leveraged for real-time fraud detection systems.

## Business Impact

This solution enables financial institutions to:

* Detect fraudulent transactions earlier
* Reduce financial losses
* Minimize false positive alerts
* Improve customer trust
* Support fraud investigation teams
* Enhance real-time risk monitoring

## Repository Structure

text
Bank-Transaction-Fraud-Detection/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Feature_Engineering.ipynb
│   ├── 03_Isolation_Forest.ipynb
│   ├── 04_Random_Forest_Model.ipynb
│   └── 05_Model_Evaluation.ipynb
│
├── models/
│   ├── isolation_forest.pkl
│   └── random_forest.pkl
│
├── visualizations/
│
├── requirements.txt
│
├── README.md
│
└── LICENSE

## Future Improvements

* Address class imbalance using SMOTE or advanced sampling techniques.
* Build a real-time fraud detection pipeline.
* Deploy the model using FastAPI or Flask.
* Integrate with streaming platforms such as Apache Kafka.
* Explore XGBoost, LightGBM, and Deep Learning models.
* Implement Explainable AI (SHAP/LIME) for model interpretability.
* Automate continuous model retraining using MLOps practices.

## Conclusion

This project demonstrates how Machine Learning can significantly improve fraud detection by combining anomaly detection with supervised classification. Through feature engineering, exploratory analysis, and predictive modeling, the solution achieved **97% accuracy** while uncovering meaningful behavioral patterns associated with fraudulent transactions.

The proposed framework provides a scalable foundation for intelligent fraud detection systems that can support real-world banking operations and reduce financial risk.
