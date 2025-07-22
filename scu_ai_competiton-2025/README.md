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
- Day-by-day experiment logging (`submissions 1–85`)

---

## 🏆 Best Performance

| Metric         | Value                                                         |
|----------------|---------------------------------------------------------------|
| **Best AUC**   | `0.902074`                                                    |
| **Best Method**| File-based **Soft Blending** of top 3 submissions             |
| **Files Used** | `11.submission`, `61.submission`, `73.submission`            |
| **Features**   | Engineered ratios + clustering + interactions                 |
| **Model(s)**   | VotingClassifier (LGBM:RF:LR = 6:2:2), but blending was model-free |
| **Date**       | 2025-07-11                                                    |
| **Award**      | 🥉 *Honorable Mention* (장려상) – SCU AI Competition 2025     |



---

## ✅ Final Summary (Submissions 81–85)

### 🥇 Final Best Score: `0.902074` (Submission 83)

After 85 carefully logged experiments, the final best result was achieved via **file-level soft blending** of the top 3 submission files (`11`, `61`, `73`).  
This blending strategy outperformed all model-level approaches, including deep stacking and feature engineering-heavy ensembles.

### 🔧 Final Strategies That Worked

- **Soft Blending** of top submission outputs (prediction-level averaging)
- **Balanced Feature Engineering**:
  - Key ratio-based features
  - Non-linear interactions
  - Carefully selected cluster features (Behavior, Purchase, Income, Time)
- **LGBMClassifier** with `RandomizedSearchCV` for tuning
- **VotingClassifier** with LGBM, RF, LR (weights = 6:2:2) as core architecture
- **Feature selection** based on importance (zero-importance pruning)
- **5-Fold Stratified CV** for stable local validation

---

### 🔚 Final Takeaway

> 🎯 _“Simple models with strong features, combined wisely, beat complex pipelines.”_

The combination of strategic blending, disciplined feature construction, and systematic experimentation led to a **Kaggle AUC of 0.902074**,  
marking a strong finish to the SCU AI Competition 2025.

🏅 This performance was officially recognized with a **🥉 Honorable Mention (장려상)** in the competition.


---

## 🗂 Folder Structure

```bash
scu_ai_competition-2025/
├── data/               # Training/test sets
├── logs/               # Experiment notes (daily logs)
├── submissions/        # Output CSVs for Kaggle submission
└── models/             # Saved models (optional)
