# 🧠 First Payment Default (FPD) Prediction Model

## 📌 Problem Statement

In lending businesses, a **First Payment Default (FPD)** occurs when a borrower misses their **first EMI after loan disbursement**.

FPD is a strong early indicator of credit risk and directly impacts portfolio quality.

---

## 🎯 Objective

Build an end-to-end machine learning system to:

* Predict probability of FPD at loan origination
* Identify high-risk borrowers early
* Enable better credit decisioning and risk segmentation

---

## 📊 Dataset

A **synthetic loan origination dataset** was created to simulate real-world lending data.

### Key Features:

* **Demographics** → Age, City Tier
* **Financials** → Income, EMI, FOIR, Loan Amount
* **Credit Behavior** → Bureau Score, Past DPD
* **Derived Metrics** → Loan-to-Income, FOIR Bands

---

## ⚙️ Project Workflow

### 1️⃣ Data Simulation

* Generated realistic loan portfolio data
* Controlled default rate (~10%) to mimic real scenarios

---

### 2️⃣ Exploratory Data Analysis (EDA)

* Identified key drivers of default
* Observed strong signals from:

  * Past DPD
  * FOIR
  * Bureau Score

---

### 3️⃣ Feature Engineering

* Created business-relevant features:

  * **FOIR (Fixed Obligation to Income Ratio)**
  * **Loan-to-Income Ratio**
  * Risk bands for key variables

---

### 4️⃣ Handling Categorical Variables

* Applied encoding techniques
* Ensured compatibility with ML models

---

### 5️⃣ Model Development

#### Baseline Model:

* Logistic Regression

#### Challenger Models:

* Random Forest
* **XGBoost (Selected Final Model)**

---

### ✅ Model Selection Logic

Although ROC-AUC was similar across models,
**XGBoost was selected because it captured more defaulters (higher recall for bads)**

👉 This aligns with real business goal:

```text
Maximize identification of risky customers
```

---

## 📈 Model Performance

| Metric       | Value                        |
| ------------ | ---------------------------- |
| ROC-AUC      | ~0.75                        |
| KS Statistic | ~0.09                        |
| Lift         | Strong top-decile separation |

---

## 📊 Lift Analysis

* Top deciles capture a large proportion of defaulters
* Model effectively ranks customers by risk

---

## 🔮 Scoring Pipeline

A realistic scoring flow was implemented:

```text
New Applications → Feature Join → Model Prediction → Probability → Risk Band → Decision
```

---

## 🧮 Risk Segmentation

Customers were segmented into:

* 🔴 High Risk
* 🟡 Medium Risk
* 🟢 Low Risk

Based on predicted probability scores.

---

## ⚖️ Credit Policy Design

Example decision strategy:

* **High Risk** → Reject / Manual Review
* **Medium Risk** → Approve with conditions
* **Low Risk** → Straight Approval

---

## 📌 Key Insights

* Past delinquency is the strongest predictor of FPD
* High FOIR significantly increases default probability
* Early risk segmentation can reduce portfolio losses

---

## 💼 Business Impact

This system can help:

* Reduce early-stage defaults
* Improve underwriting decisions
* Optimize credit approval strategies

---

## 🛠️ Tech Stack

* Python (pandas, numpy)
* scikit-learn
* XGBoost
* Matplotlib

---

## 🚀 Future Improvements

* Probability calibration
* SHAP-based explainability
* Deployment as API
* Real-world dataset validation

---

## 👨‍💻 Author

Venki
Data Analyst | Risk Analytics | Machine Learning

---
