# 🧠 SCU AI Competition 2025 - Campaign Response Prediction

This repository contains my full pipeline and experiments for the **3rd SCU AI Competition (2025)**.  
The task was to predict whether a customer would accept a marketing campaign based on structured survey data.

---

## 🎯 Objective

- Build a high-performing binary classification model (Target: `Response`)
- Handle missing values and categorical features effectively
- Apply extensive **feature engineering** (ratios, interactions, clustering)
- Explore ensemble methods and blending strategies
- Track experiments systematically with daily logs

---

## 📊 Dataset

- **Source**: Official SCU AI Competition dataset  
- **Format**: Tabular data with categorical, numerical, and behavioral variables  
- **Target**: `Response`  
- **Metric**: AUC (Area Under ROC Curve)

Key challenges:
- Many missing values across features
- Strong non-linear patterns
- Need for domain-inspired feature engineering

---

## 🧪 Techniques Applied

- **Preprocessing**
  - Missing value imputation (`mode`, `median`)
  - Scaling (`StandardScaler`)
  - Encoding (`LabelEncoder` for categorical)

- **Feature Engineering**
  - Aggregates (e.g., total purchases, total spend)
  - Ratios (e.g., purchases-to-income, visits-to-recency)
  - Domain-inspired interactions (e.g., wine × campaign responsiveness)
  - **Clustering (`KMeans`)**:
    - Purchase styles
    - Behavioral patterns
    - Income-related usage
    - Time/recency groups

- **Modeling**
  - RandomForest, LightGBM, Logistic Regression
  - VotingClassifier (weights tuned)
  - StackingClassifier (select trials)
  - **Optuna** for hyperparameter optimization

- **Evaluation**
  - Local: 5-Fold Stratified CV (AUC)
  - Public leaderboard on Kaggle
  - Daily experiment tracking (`logs/`)

---

## 📈 Experiments & Submissions

- **Total submissions**: 85 (2025-06-23 → 2025-07-11)  
- **Logs**: stored in [`logs/`](./logs)  
  - Each file = date-based log of experiments (`YYYYMMDD_experiment_log.md`)  
  - Includes validation AUC, Kaggle AUC, notes

Highlights:
- `20250629_experiment_log.md` → First cluster-based features  
- `20250703_experiment_log.md` → Optuna-tuned RF/LGBM  
- `20250711_experiment_log.md` → Final blending strategy (`0.902074` AUC)

---

## 🏆 Best Result

- **Final AUC**: `0.902074` (Kaggle public LB)  
- **Method**: **Soft Blending** of 3 best submissions (`11`, `61`, `73`)  
- **Features**: Ratios + clustering + interaction terms  
- **Core Models**: LightGBM, RF, Logistic Regression (Voting 6:2:2)  
- **Recognition**: 🥉 *Honorable Mention (장려상)*

---

## 📚 What I Learned

- **Blending beats stacking**: Simple file-level soft blending outperformed complex model-level ensembles  
- **Features > Models**: Well-designed ratios and clusters had more impact than exotic models  
- **Optuna ≠ Kaggle success**: Highest local validation AUC didn’t guarantee leaderboard boost  
- Importance of **systematic logging**: Daily logs made progress traceable and reproducible

---

## 📁 Folder Structure

```bash

scu_ai_competition-2025/
├── data/               # Competition dataset
├── logs/               # Daily experiment logs (85 total)
├── submissions/        # Output CSVs for Kaggle
├── models/             # Saved models (optional)
├── requirements.txt    # Dependencies
└── README.md           # Project overview

```

---

✍️ Maintained by hojjang98

Final Kaggle AUC: 0.902074 · Awarded Honorable Mention 🥉
