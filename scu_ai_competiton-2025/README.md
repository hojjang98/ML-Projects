# 🧠 SCU AI Competition 2025 - Campaign Response Prediction

This project was submitted for the **3rd SCU AI Competition** hosted on Kaggle:
🔗 [Official Competition Page](https://www.kaggle.com/competitions/3-ai)

The objective is to predict whether an individual will **accept a marketing campaign** using tabular personal and demographic data.

---

## 📊 Task Overview

* **Problem Type**: Binary Classification
* **Target**: `Response` (1 = Accepted, 0 = Rejected)
* **Metric**: AUC (Area Under the ROC Curve)
* **Data**: Survey-based structured dataset with missing values and categorical variables

---

## 🧪 Techniques Applied

● Missing value imputation (mode / median)
● Feature scaling (StandardScaler) and one-hot encoding
● Ensemble modeling (VotingClassifier, StackingClassifier)
● Hyperparameter tuning with Optuna
● Best model tracking day-by-day
● LightGBM, RandomForest, GradientBoosting
● Feature interaction engineering (submission 10, 14)
● Clustering-based feature engineering using KMeans (submission 11, 13)

---

## 🗂 Folder Structure

```bash
scu_ai_competiton-2025/
├── data/
├── logs/
├── submission/
└── models/
```

---

## 🏆 Best Performance

* **Best AUC**: `0.8973`
* **Model**: Optuna-tuned `LGBMClassifier` + KMeans clustering feature (n=4)
* **Submission**: `11.submission`
* **Date**: 2025-06-25

---

## 🔧 Tech Stack

* Python 3.x
* scikit-learn, LightGBM, XGBoost
* Optuna
* pandas, numpy, matplotlib

---

## 📌 Notes

* All experiments are tracked by date with versioned model scripts.
* Preprocessing is integrated within each model pipeline.
* This structure emphasizes **reproducibility**, **experiment traceability**, and **progress logging**.
* Feature engineering includes domain-inspired aggregates, interaction features, and **cluster-based segmentation**.
* Optuna consistently outperformed RandomizedSearchCV for LGBM.
* Interestingly, the **simplest tuned model (LGBM only)** initially performed best, but clustering-based feature engineering ultimately achieved the **highest AUC**.

📂 Dataset is not included. Please refer to the [Kaggle competition page](https://www.kaggle.com/competitions/3-ai) to download the data.
