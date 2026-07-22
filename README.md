# 📊 Dataset Overview
The project utilizes the KPI educator assessment dataset (KPI_data_for_logit_model.csv), which includes key performance indicators, questionnaire statistics, average grades, and net promoter scores (NPS).
Target Variable (X502010_1): A binary indicator representing a specific performance tier or target outcome.
Key Features Used:
KPI_assessment_1: Initial KPI assessment score.
Number.of.questionnaires_1: Volume of student feedback questionnaires processed.
Average_grade_1: Mean grading score assigned.
NPS_1: Net Promoter Score reflecting student satisfaction.
Additional_achievement_1: Count of additional professional achievements.
⚙️ Methodology & Modeling Pipeline
Data Preparation & Splitting:
Filtered relevant features and separated the target variable (X502010_1).
Performed an 80-20 stratified train-test split to preserve class balance.
Model Training with Cross-Validation:
Random Forest Classifier: Tuned hyperparameters (n_estimators and max_depth) using 5-fold cross-validation with ROC-AUC scoring via GridSearchCV.
Gradient Boosting Classifier: Optimized learning rates, tree depth, and estimator counts through rigorous grid search.
Evaluation & Threshold Tuning:
Generated predicted probabilities (predict_proba) on the unseen test set.
Built Receiver Operating Characteristic (ROC) curves and computed the Area Under the Curve (ROC-AUC).
Applied Youden’s J statistic to identify the optimal decision threshold, balancing false positives and false negatives.
🚀 Getting Started & Installation
Prerequisites
Ensure you have Python 3.8+ installed. You will need the following data science libraries:
Bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
Running the Notebook
Clone this repository to your local machine:
Bash
git clone [https://github.com/your-username/rf-boosting-roc-classification.git](https://github.com/your-username/rf-boosting-roc-classification.git)
cd rf-boosting-roc-classification
Launch Jupyter Notebook:
Bash
jupyter notebook 4-RF-Boosting.ipynb
Run all cells sequentially to reproduce the data preprocessing, model tuning, cross-validation scores, and ROC visualizations.
📈 Key Results Summary
Random Forest Performance: Delivered robust cross-validated performance with an ROC-AUC score of approximately 0.859 (optimized with max depth 5 and 50 estimators).
Gradient Boosting Performance: Reached a strong competitive cross-validated ROC-AUC score of approximately 0.849 (tuned with a learning rate of 0.2, depth 3, and 50 estimators).
Presentation: A detailed executive summary of these findings, metric comparisons, and ROC curve plots can be found in 4-RF-Boosting.pptx.
