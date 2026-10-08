Customer Churn Prediction & Retention Analytics

A machine learning project focused on predicting customer churn and identifying customers who are at higher risk of leaving. The project compares multiple classification algorithms, addresses class imbalance, and applies hyperparameter optimization to improve churn detection.

📌 Project Overview

Customer churn is a major business problem where identifying customers likely to leave can help organizations take preventive retention actions.

This project develops an end-to-end machine learning pipeline covering:

Data preprocessing and cleaning
Categorical feature encoding
Train-test splitting
Feature scaling
Class imbalance handling
Multiple classification algorithms
Cross-validation
Hyperparameter optimization
Model evaluation using precision, recall, and F1-score
Model serialization using Joblib
🛠️ Technologies Used
Python
Pandas
NumPy
Scikit-learn
XGBoost
Imbalanced-learn
Optuna
Matplotlib / Seaborn
Joblib
🤖 Models Evaluated

The project compares the following classification models:

Decision Tree
Random Forest
AdaBoost
XGBoost

XGBoost was further optimized using both RandomizedSearchCV and Optuna.

⚖️ Handling Class Imbalance

Since churn prediction involves an imbalanced target variable, multiple techniques were evaluated:

SMOTE
ADASYN
SMOTEENN
Class Weighting
scale_pos_weight for XGBoost

The models were evaluated using metrics that are more informative for churn detection than accuracy alone.

📊 Model Evaluation

The primary evaluation metrics used were:

Precision
Recall
F1-Score
Accuracy
5-Fold Cross-Validation F1-Score

The final optimized XGBoost model achieved approximately:

0.63 Cross-Validation F1-Score
75% Recall for churned customers
0.59 Test F1-Score
73% Test Accuracy

The focus was particularly on churn recall, since missing a customer who is likely to churn can result in a missed retention opportunity.

🔍 Hyperparameter Optimization

XGBoost was optimized using:

RandomizedSearchCV

Hyperparameters such as:

Learning rate
Number of estimators
Maximum tree depth
Subsample ratio
Column sampling
Minimum child weight
Gamma
Class weighting

were tuned using cross-validation.

Optuna

Optuna was then used for automated hyperparameter optimization across multiple trials to identify a stronger combination of model parameters based on cross-validation F1-score.

📁 Project Structure
Customer-Churn-Prediction/
│
├── Customer-Churn.csv
├── ML_Model_Building.ipynb
├── ada_boost_churn_model.pkl
└── README.md
🚀 Workflow
Raw Dataset
     ↓
Data Cleaning & Preprocessing
     ↓
Categorical Encoding
     ↓
Train-Test Split
     ↓
Feature Scaling
     ↓
Class Imbalance Handling
     ↓
Model Training
     ↓
Cross-Validation
     ↓
Hyperparameter Optimization
     ↓
Model Evaluation
     ↓
Best Model Selection
💡 Key Takeaways
Accuracy alone is not sufficient for evaluating churn prediction models.
Recall is particularly important when the objective is to identify as many potential churners as possible.
Imbalanced datasets can significantly affect classification performance.
Cross-validation provides a more reliable estimate of model performance.
Hyperparameter optimization can improve model performance compared with default model settings.
🔮 Future Improvements

Potential extensions of this project include:

Feature importance and explainability using SHAP
Threshold optimization based on retention campaign costs
Deployment using Flask/FastAPI or Streamlit
Real-time churn prediction
Customer segmentation combined with churn probability
Integration with a retention recommendation system
👨‍💻 Author

Dhairya Arora
B.Tech Biotechnology, Delhi Technological University (DTU)
