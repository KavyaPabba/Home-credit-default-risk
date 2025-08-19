Home Credit Default Risk – Fair AI in Finance

This project uses the Kaggle Home Credit Default Risk competition as a real-world case study to explore how AI models in finance can be both accurate and fair.
The focus goes beyond prediction performance—we also dig into explainability and fairness auditing, which are increasingly important for building trustworthy financial systems in line with emerging regulations like the EU AI Act.

What’s Inside
	•	homecredit.ipynb → main notebook: data prep, modeling, explainability, fairness checks
	•	baseline_model_comparison.csv → first performance benchmark of Logistic Regression vs LightGBM
	•	shaplike_global_importance.csv → feature importance ranking (SHAP values)
	•	local_explain_* → case-level SHAP explanations (high risk, low risk, borderline)
	•	fairness_by_gender.csv → fairness metrics split by gender
	•	fairness_by_age_group.csv → fairness metrics split by age groups
	•	week3_mitigation_comparison.csv → results of fairness mitigation experiments
	•	Home_Credit_Final_Report_v2.docx → polished write-up combining all findings

Workflow at a Glance
	1.	Data Preparation → Combine multiple Home Credit tables (application, bureau, previous loans). Clean and impute missing values. Create new variables (credit utilization, repayment ratios, etc.).
	2.	Modeling → Compare two approaches: Logistic Regression (simple, interpretable) vs. LightGBM (non-linear, high performance).
	3.	Evaluation → Measure AUC, accuracy, precision, and recall.
	4.	Explainability → Use SHAP to see which features matter globally, and to explain individual applicants’ risk scores.
	5.	Fairness → Audit selection rates, true positive rates, and false positive rates across gender and age groups.
	6.	Mitigations → Apply re-weighting, threshold adjustment, and post-processing to reduce disparities.

Key Takeaways
	•	Performance → LightGBM was best overall (AUC 0.778, Accuracy 0.757), but Logistic Regression wasn’t far behind.
	•	Precision problem → Both models had <20% precision, meaning lots of false alarms when predicting default.
	•	Top predictors → External credit scores (EXT_SOURCE_1–3) and loan amount variables were the strongest signals.
	•	Fairness →
	•	Males and younger applicants were flagged more often. This improved detection (higher TPR) but also created more false positives.
	•	Older applicants were flagged less often, leading to more missed defaults.

Policy & Practice Recommendations
	•	Require regular fairness audits with clear, transparent metrics.
	•	Standardize explainability reports (e.g., SHAP summaries) for both regulators and consumers.
	•	Explore fairness-aware modeling (re-weighting, constraints, threshold tuning).
	•	Improve data governance and make credit decision thresholds transparent.
	•	Align model development with EU AI Act requirements for high-risk financial AI systems.

How to Reproduce
	1.	Download Kaggle Home Credit Default Risk data into your working folder.
	2.	Open homecredit.ipynb in Jupyter/Colab/VS Code.
	3.	Run the notebook step-by-step.
	4.	Outputs (CSV files + the final report) will be generated automatically.

Why This Matters

This project is part of a PhD portfolio on AI in Finance. The goal is to show how a credit risk model can be developed end-to-end—from raw data, through explainability, to fairness mitigation—so that it’s not only high-performing, but also regulator-ready and socially responsible.
