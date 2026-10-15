# credit-card---default---prediction
# Credit Card Default Prediction & Risk Analysis

An interactive Streamlit dashboard that predicts whether a credit card customer will default on their next payment, compares statistical models, and explores how decision thresholds affect lending outcomes.

## Features
- **Dataset overview:** customer count, default rate, repayment distributions
- **EDA dashboard:** correlation heatmap, payment patterns, credit limit vs. default
- **Model comparison:** Logistic Regression, LDA and Random Forest (accuracy, precision, recall, F1, ROC-AUC)
- **Risk prediction:** predicted default probability for a customer, with what-if adjustments
- **Threshold analysis:** change the classification threshold and see precision/recall change, plus a cost-based optimal threshold
- **Explainability & ethics:** feature importance, fairness check by sex, education and age group, and a discussion of limitations and bias

## Dataset
UCI "Default of Credit Card Clients" (30,000 customers, Taiwan, 2005).
Download the CSV (e.g. `UCI_Credit_Card.csv` from Kaggle) and place it in the project folder, or upload it from the app sidebar.

## How to run
```
pip install -r requirements.txt
streamlit run credit_default_app.py
```

## Method
- 80/20 stratified train/test split
- Logistic Regression and LDA use standardized features; Random Forest uses 200 trees
- Logistic Regression and Random Forest use balanced class weights because only about 22% of customers default
- Models are compared with recall, F1 and ROC-AUC, not just accuracy

## Limitations
- Data is from one country and one time period, so it may not generalize
- Sensitive attributes (sex, age, marriage, education) can cause biased outcomes, and other features may act as proxies
- Feature importance shows association, not causation
- The classification threshold is a policy choice that should reflect business costs
- Educational project only. It is not a validated credit-scoring system

## Reference
Based on an open-access research study comparing Logistic Regression, LDA, SVM, Random Forest, XGBoost and neural networks on the same problem. This project reproduces a smaller subset and adds a cost-based threshold analysis and a fairness check.

