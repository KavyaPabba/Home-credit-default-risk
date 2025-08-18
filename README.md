# Home Credit Default Risk – Fair AI in Finance

This project explores the [Kaggle Home Credit Default Risk competition](https://www.kaggle.com/competitions/home-credit-default-risk) as a case study in **AI for Finance**, focusing on predictive performance **and** fairness/explainability for regulatory alignment.

## 📂 Project Structure
- `homecredit.ipynb` – Main analysis (data prep, modeling, explainability, fairness)
- `baseline_model_comparison.csv` – Baseline model metrics
- `shaplike_global_importance.csv` – Global SHAP feature importance
- `local_explain_highrisk.csv` – Local SHAP for high-risk cases
- `local_explain_lowrisk.csv` – Local SHAP for low-risk cases
- `local_explain_borderline.csv` – Local SHAP for borderline cases
- `fairness_by_gender.csv` – Fairness metrics by gender
- `fairness_by_age_group.csv` – Fairness metrics by age group
- `week3_mitigation_comparison.csv` – Fairness mitigation experiments
- `Model Performance and Fairness Analysis for Home Credit.docx` – Original draft report
- `Home_Credit_Final_Report_v2.docx` – Final polished report (this repo)

## 🚀 Workflow
1. **Data Preparation** – Merge application/bureau/previous loans; impute missing values; engineer credit utilization, repayment history, ratios.
2. **Modeling** – Logistic Regression (baseline, interpretable) vs. LightGBM (non-linear). Train/val/test with cross-validation.
3. **Evaluation** – AUC, accuracy, precision, recall.
4. **Explainability** – Global SHAP for feature ranking; local SHAP for case-level reasoning.
5. **Fairness** – Selection rate, TPR (equal opportunity), FPR across gender and age groups.
6. **Mitigations** – Threshold tuning and re-weighting experiments (`week3_mitigation_comparison.csv`).

## 📊 Key Results
- **Best overall**: LightGBM (AUC 0.778; Accuracy 0.757). Logistic Regression close (AUC 0.767; Accuracy 0.707).
- **Precision challenge**: < 0.20 for both models → many false alarms among predicted defaults.
- **Top predictors**: External credit scores (EXT_SOURCE_1–3); loan size variables.
- **Fairness**:
  - Males and younger applicants flagged more frequently → higher detection but more false positives.
  - Older applicants flagged less often → more missed defaults.

## 🏛️ Policy Recommendations (Summary)
- Mandate **fairness audits** with clear metrics.
- Standardize **explainability** (e.g., SHAP) for regulators and consumers.
- Use **fairness-aware modeling** (re-weighting, thresholds, post-processing).
- Strengthen **data governance** and transparency in **decision thresholds**.
- Align with **EU AI Act** principles for high-risk AI systems.

## 🧪 Reproducibility
- Open `homecredit.ipynb` in Jupyter/Colab.
- Ensure Kaggle data is available under the working directory according to competition terms.
- Run cells sequentially; outputs (CSVs and the final report) will be produced in the working directory.

## 🎯 Purpose
This repository is part of a **PhD portfolio project** (AI in Finance), demonstrating end-to-end modeling with fairness and explainability for regulator-ready reporting.
