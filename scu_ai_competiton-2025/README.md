# 🧠 SCU AI Competition 2025 - Campaign Response Prediction

This repository contains our solution to the **3rd SCU AI Competition** hosted on Kaggle:  
🔗 [Official Competition Page](https://www.kaggle.com/competitions/3-ai)

The objective is to predict whether an individual will **accept a marketing campaign**, based on structured personal, behavioral, and demographic data.

---

## 📊 Task Overview

* **Problem Type**: Binary Classification
* **Target**: `Response` (1 = Accepted, 0 = Rejected)
* **Metric**: AUC (Area Under the ROC Curve)
* **Data**: Survey-based tabular dataset with missing values and categorical variables

---

## 🧪 Techniques Applied

* Missing value imputation (mode / median)
* Feature scaling using `StandardScaler`
* Categorical encoding with one-hot encoding
* Hyperparameter optimization using **Optuna**
* Model ensembling (VotingClassifier, StackingClassifier)
* Feature engineering: interaction terms, aggregated totals
* Cluster-based segmentation using **KMeans** (submission 11, 13)
* Day-by-day experiment logging and model versioning (submissions 1–20)
* LightGBM as core model, with comparison to RandomForest, GradientBoosting

---

## 🗂 Folder Structure

```bash
scu_ai_competition-2025/
├── data/
├── logs/
├── submissions/
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

📌 Notes
*All experiments are tracked and logged per submission.
*Preprocessing is embedded within each pipeline to ensure reproducibility.
*Feature engineering combines domain insights, interaction features, and unsupervised segmentation.
*Optuna consistently outperformed RandomizedSearchCV for LGBM.
*While a simple Optuna-tuned LGBM performed strongly, cluster-based features ultimately achieved the highest AUC.

📂 Dataset is not included. Please refer to the [Kaggle competition page](https://www.kaggle.com/competitions/3-ai) to download the data.
