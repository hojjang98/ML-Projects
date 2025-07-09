# 🧠 SCU AI Competition 2025 - Campaign Response Prediction

This repository contains my solution to the **3rd SCU AI Competition** hosted on Kaggle:  
🔗 [Official Competition Page](https://www.kaggle.com/competitions/3-ai)

The task is to predict whether a customer will accept a marketing campaign, based on structured survey data.

---

## 📊 Task Overview

- **Problem Type**: Binary Classification  
- **Target**: `Response` (1 = Accepted, 0 = Rejected)  
- **Metric**: AUC (Area Under the ROC Curve)  
- **Data**: Tabular dataset with missing values, categorical variables, and behavioral signals

---

## 🧪 Techniques Applied

- Missing value imputation (`mode`, `median`)
- Feature scaling with `StandardScaler`
- Categorical encoding using `LabelEncoder`
- Extensive feature engineering:
  - Aggregated totals (e.g., total purchases)
  - Ratio features (e.g., purchase-to-income)
  - Behavioral indicators (e.g., site visits / recency)
  - Non-linear interactions (e.g., wine × campaign responsiveness)
- 4-way clustering with `KMeans`:
  - Behavior patterns
  - Purchase styles
  - Income-related behavior
  - Time-based usage patterns
- Model ensembling:
  - `VotingClassifier` (LGBM, RF, LR)
  - `StackingClassifier` (select submissions)
- Hyperparameter tuning:
  - `RandomizedSearchCV`
  - `Optuna` (for single-model optimization)
- Local evaluation via 5-Fold `StratifiedKFold` + AUC
- Day-by-day experiment logging (`submissions 1–75`)

---

## 🏆 Best Performance (as of Submission 73)

| Metric        | Value                     |
|---------------|---------------------------|
| **Best AUC**  | `0.900233`                |
| **Model**     | `VotingClassifier (LGBM:RF:LR = 6:2:2)` |
| **Features**  | Engineered ratios + 4 clustering types |
| **Tuning**    | LGBM tuned via `RandomizedSearchCV` |
| **Submission**| `73.submission`           |
| **Date**      | 2025-07-09                |

---

## 🗂 Folder Structure

```bash
scu_ai_competition-2025/
├── data/               # Training/test sets
├── logs/               # Experiment notes (daily logs)
├── submissions/        # Output CSVs for Kaggle submission
└── models/             # Saved models (optional)
