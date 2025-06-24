# 🧠 SCU AI Competition 2025 - Campaign Response Prediction

This project was submitted for the **3rd SCU AI Competition** hosted on Kaggle:  
🔗 [Official Competition Page](https://www.kaggle.com/competitions/3-ai)

The objective is to predict whether an individual will **accept a marketing campaign** using tabular personal and demographic data.

---

## 📊 Task Overview

- **Problem Type**: Binary Classification
- **Target**: `Response` (1 = Accepted, 0 = Rejected)
- **Metric**: AUC (Area Under the ROC Curve)
- **Data**: Survey-based structured dataset with missing values and categorical variables

---

## 🧪 Techniques Applied

 Missing value imputation (mode / median)  
 Feature scaling (StandardScaler) and one-hot encoding  
 LightGBM, RandomForest, LogisticRegression  
 Ensemble modeling using VotingClassifier  
 Hyperparameter tuning with Optuna  
 Best model tracking day-by-day

---

## 🗂 Folder Structure

```bash
scu_ai_competiton-2025/
├── data/
├── logs/
├── submission/
└── models/
'''

---

## 🏆 Best Performance

- **Best AUC**: `0.8515`  
- **Model**: Optuna-tuned VotingClassifier (LGBM + RF + LogisticRegression)  
- **Date**: 2025-06-23

---

## 🔧 Tech Stack

- Python 3.x
- scikit-learn, LightGBM, XGBoost
- Optuna
- pandas, numpy, matplotlib

---

## 📌 Notes

All experiments are tracked by date with versioned model scripts.  
Preprocessing is integrated within each model pipeline.  
This structure emphasizes **reproducibility**, **experiment traceability**, and **progress logging**.

📂 Dataset is not included. Please refer to the [Kaggle competition page](https://www.kaggle.com/competitions/3-ai) to download the data.


