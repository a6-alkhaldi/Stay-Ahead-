# Stay Ahead – Customer Churn Prediction System

This repository contains a complete machine learning pipeline for customer churn prediction, developed as part of the Samsung Innovation Campus.

The goal of the project is to predict which customers are likely to churn by experimenting with range of models (Traditional and Deep models), understand the factors influencing churn, and support proactive business decisions such as targeted retention campaigns.

---

## 📌 Project Overview
Customer churn is a major challenge for subscription-based services, as retaining existing customers is significantly more cost-effective than acquiring new ones.  
This project builds and evaluates multiple machine learning models to classify customers into **churn vs non-churn**, with a strong focus on **maximizing recall** to reduce missed churn cases.

---

## 🎯 Objectives
- Analyze customer behavior and identify key churn drivers  
- Build and compare multiple machine learning models  
- Handle class imbalance using appropriate evaluation strategies  
- Deliver a practical, business-oriented AI solution  

---

## 🧠 Models Implemented
- Logistic Regression (Baseline)
- Random Forest
- **XGBoost (Final Selected Model)**
- TabNet
- NODE (Neural Oblivious Decision Ensembles)

The final model (**XGBoost**) was selected based on its superior balance between **Recall and F1-score**, making it more effective for churn-sensitive applications.

---

## 📊 Dataset
- **Source:** We use the Telco Customer Churn dataset available on Kaggle: https://www.kaggle.com/datasets/blastchar/telco-customer-churn The dataset includes 7,043 customers.
- **Features include:**
  - Demographics (gender, partner, dependents)
  - Services (internet, streaming, security, tech support)
  - Contracts (contract type, payment method)
  - Financials (monthly and total charges)
- **Target Variable:** Churn (Yes / No)


---

## 🛠️ Preprocessing
- Removal of invalid `TotalCharges` values  
- Handling missing data  
- One-Hot Encoding for categorical features  
- Standardization of numerical features  
- Stratified train/test split  
- Class imbalance handling using:
  - Class weighting
  - Threshold tuning  

---

## 🔬 Methodology
1. **Logistic Regression (Baseline)**  
   - Simple and interpretable baseline model  

2. **Random Forest**  
   - Captures non-linear feature interactions  
   - Tuned using Randomized Search  

3. **XGBoost (Final Model)**  
   - Gradient boosting algorithm  
   - Tuned using **Bayesian Optimization (Optuna)**  
   - Achieved the strongest recall and ROC-AUC  

4. **Deep Tabular Models**
   - **TabNet**
     - Sequential attention-based architecture  
     - Interpretable feature masks  
   - **NODE**
     - Tree-inspired neural architecture  
     - Tuned using Optuna  
     - Strong performance but higher computational cost  

---

## 📈 Evaluation Strategy
- 5-Fold Stratified Cross-Validation  
- **Primary Metric:** Recall  
- Additional metrics:
  - Precision
  - F1-score
  - Accuracy
  - ROC-AUC  

Threshold tuning was applied to further improve churn detection in the minority class.

---

## 🚀 Results Summary
- **XGBoost achieved ~80% recall** on churn customers  
- Strong ROC-AUC of ~0.84  
- Best trade-off between sensitivity and robustness  
- Deep models (TabNet, NODE) showed competitive results but required careful tuning  

Overall, XGBoost consistently delivered the most reliable performance.

---


## 🖥️ System Deployment
- **Backend:** FastAPI (REST API)
  - `/predict` for churn probability scoring  
  - `/high-risk-users` for dashboard integration  
- **Frontend:** HTML, CSS, JavaScript  
- Real-time churn prediction dashboard  
- English & Arabic language support  

---

## 📎 Demo
🎥 Demo Video: https://youtu.be/i7YS-S6PKHw

---

## 📌 Notes
This project was completed for educational purposes as part of the **Artificial Intelligence Program at Samsung Innovation Campus**.
