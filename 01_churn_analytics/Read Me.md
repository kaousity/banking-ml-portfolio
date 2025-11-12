# 🧩 Customer Churn Prediction Project — Executive Summary & README

### 🎯 Project Overview
This project predicts customer churn using the **Telco Customer Churn** dataset and frames it as a **financial retention problem**.  
It demonstrates an end-to-end data science workflow — from **EDA and feature engineering** to **modeling, evaluation, and SHAP explainability** — with a strong focus on interpretability and business value.

---

## 📘 Objective
Predict which customers are likely to churn (close accounts or stop using services) and **explain why**, enabling proactive retention strategies.

**Business Value:**  
Reducing churn by just 5 % can translate to millions in retained revenue for subscription-based or financial institutions.

---

## 🧰 Tools & Stack
`Python` • `Pandas` • `NumPy` • `Scikit-Learn` • `XGBoost` • `Matplotlib` • `Seaborn` • `SHAP` • `Jupyter Notebook` • `Tableau` / `Plotly`

---

## 🧠 Workflow Summary

**Step 1 — Data Understanding & Cleaning**  
- 7 043 rows × 21 columns  
- Cleaned missing `TotalCharges`, dropped `customerID`, encoded categoricals.

**Step 2 — Exploratory Data Analysis (EDA)**  
- Churn rate ≈ 26.5 %.  
- Higher churn for **month-to-month** contracts, **high monthly charges**, and **no add-on services**.

**Step 3 — Modeling**  
- Compared **Logistic Regression**, **XGBoost**, **Random Forest** using Accuracy, Recall, Precision, F1, and ROC-AUC.

**Step 4 — Explainability**  
- Used **SHAP** to identify most impactful churn drivers.

**Step 5 — Insights & Actions**  
- Translated model results into concrete retention recommendations.

---

## 📊 Modeling Results

| Model | Accuracy | Recall | Precision | F1 | ROC-AUC | Notes |
|-------|-----------|--------|------------|----|----------|--------|
| **Logistic Regression** | 0.803 | 0.548 | 0.654 | 0.596 | 0.845 | Best balance & interpretability |
| XGBoost | 0.785 | 0.521 | 0.611 | 0.562 | 0.823 | Slightly lower AUC, more flexibility |
| Random Forest | 0.788 | 0.454 | 0.640 | 0.531 | 0.821 | Overfitting tendency |

**Champion Model:** Logistic Regression — highest AUC & F1, simplest to deploy and explain.

---

## 🧮 SHAP Explainability

Top positive (churn-increasing) drivers →  
- Short tenure  
- Month-to-month contracts  
- High monthly charges  
- Electronic check payment  
- Lack of support/security add-ons  

Top negative (retention) drivers →  
- Long tenure  
- Two-year contracts  
- Lower charges  
- Bundled services  

![SHAP Summary](images/shap_summary.png)

---

## 💡 Business Insights & Recommended Actions

| Insight | Recommended Action |
|----------|-------------------|
| New customers churn more | Implement early onboarding + retention offers |
| Month-to-month contracts churn most | Incentivize annual or multi-year plans |
| High monthly charges increase churn | Introduce tiered pricing or loyalty discounts |
| Customers lacking add-ons churn more | Bundle services (security, support, backup) |
| Electronic check users churn more | Promote digital autopay & paperless billing |

---

## 🚀 Next Steps
- Tune XGBoost hyperparameters (learning rate, max_depth).  
- Adjust classification threshold to boost recall.  
- Build a **Streamlit app** for live churn scoring.  
- Track experiments with **MLflow**.

---

## 📁 Repository Structure
```
01_churn_analytics/
│
├── data/
│   └── Telco-Customer-Churn.csv
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Modeling.ipynb
│   ├── 03_SHAP_Explainability.ipynb
├── reports/
│   ├── churn_report.pdf
│   └── churn_dashboard.twbx
├── images/
│   └── shap_summary.png
└── README.md
```

---

## 🗣️ Interview Talking Points
> “I built an end-to-end churn model that achieved **84 % AUC** using Logistic Regression.  
> My EDA showed churn is driven by short tenure, month-to-month contracts, and high monthly charges.  
> SHAP confirmed these drivers, making the results explainable and actionable for retention teams.”
