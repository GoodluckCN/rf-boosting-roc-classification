# Homework 4: Random Forest, Boosting & ROC Analysis

This repository contains the complete code, dataset, and presentation materials for **Homework 4** of the Applied Machine Learning course. The project explores advanced ensemble learning methods—specifically **Random Forest** and **Gradient Boosting**—and evaluates their classification performance using **ROC curves** and optimal threshold tuning.

---
# Dataset Overview
The project utilizes the KPI educator assessment dataset (KPI_data_for_logit_model.csv), which includes key performance indicators, questionnaire statistics, average grades, and net promoter scores (NPS).
Target Variable (X502010_1): A binary indicator representing a specific performance tier or target outcome.
- Key Features Used:
- KPI_assessment_1: Initial KPI assessment score.
- Number.of.questionnaires_1: Volume of student feedback questionnaires processed.
- Average_grade_1: Mean grading score assigned.
- NPS_1: Net Promoter Score reflecting student satisfaction.
- Additional_achievement_1: Count of additional professional achievements.

# ⚙️ Methodology & Modeling Pipeline
- Data Preparation & Splitting:
Filtered relevant features and separated the target variable (X502010_1).
Performed an 80-20 stratified train-test split to preserve class balance.

- Model Training with Cross-Validation:
Random Forest Classifier: Tuned hyperparameters (n_estimators and max_depth) using 5-fold cross-validation with ROC-AUC scoring via GridSearchCV.
Gradient Boosting Classifier: Optimized learning rates, tree depth, and estimator counts through rigorous grid search.

- Evaluation & Threshold Tuning:
Generated predicted probabilities (predict_proba) on the unseen test set.
Built Receiver Operating Characteristic (ROC) curves and computed the Area Under the Curve (ROC-AUC).
Applied Youden’s J statistic to identify the optimal decision threshold, balancing false positives and false negatives.

# 📈 Key Results Summary
- Random Forest Performance: Delivered robust cross-validated performance with an ROC-AUC score of approximately 0.859 (optimized with max depth 5 and 50 estimators).
- Gradient Boosting Performance: Reached a strong competitive cross-validated ROC-AUC score of approximately 0.849 (tuned with a learning rate of 0.2, depth 3, and 50 estimators).
- Presentation: A detailed executive summary of these findings, metric comparisons, and ROC curve plots can be found in 4-RF-Boosting.pptx.

## 📁 Repository Structure

```text
├── KPI_data_for_logit_model.csv   # Primary dataset containing educator performance metrics
├── 4-RF-Boosting.ipynb            # Jupyter Notebook with full modeling pipeline & experiments
├── 4-RF-Boosting.pptx             # Final summary presentation slides (max 6 slides)
├── 3-CART.ipynb                   # Previous lab reference notebook (Decision Trees)
├── 3-CART.pptx                    # Previous lab presentation slides
└── README.md                      # Project documentation

