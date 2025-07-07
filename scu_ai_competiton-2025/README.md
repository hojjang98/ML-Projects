# 🧠 SCU AI Competition 2025 - Campaign Response Prediction

This repository contains my solution to the **3rd SCU AI Competition** hosted on Kaggle:  
🔗 [Official Competition Page](https://www.kaggle.com/competitions/3-ai)

The task is to predict whether a customer will accept a marketing campaign, based on structured survey data.

---

## 📊 Task Overview

* **Problem Type**: Binary Classification
* **Target**: `Response` (1 = Accepted, 0 = Rejected)
* **Metric**: AUC (Area Under the ROC Curve)
* **Data**: Tabular dataset with missing values, categorical variables, and behavioral features

---

## 🧪 Techniques Applied

* Missing value imputation (mode / median)
* Feature scaling with `StandardScaler`
* Categorical encoding (`LabelEncoder`)
* Feature engineering with:
  - Aggregated totals (e.g., total purchases)
  - Ratio features (e.g., purchase/income)
  - Interaction terms (e.g., wine × campaign acceptance)
* Unsupervised clustering using `KMeans` (behavior & purchase pattern segmentation)
* Model ensembling:
  - `VotingClassifier` (LGBM, RF, LR)
  - `StackingClassifier` (some experiments)
* Hyperparameter tuning with **Optuna**
* Day-by-day experiment tracking (submissions 1–65)

---

## 🏆 Best Performance

* **Best AUC**: `0.897686`
* **Model**: `VotingClassifier (LGBM:RF:LR = 6:2:2)`  
  with engineered features + clustering (n=4)
* **Submission**: `61.submission`
* **Date**: 2025-07-07

---

## 🗂 Folder Structure

```bash
scu_ai_competition-2025/
├── data/
├── logs/
├── submissions/
└── models/
