# 🏦 Loan Grade & Diabetes Classification (SCU AI Competition – Excellence Award)

This repository documents my participation in the **2nd AI Competition hosted by Seoul Cyber University**,  
where I worked on two separate classification challenges:

- **Loan Grade Prediction** (multi-class classification)  
- **Diabetes Prediction** (binary classification)

---

## 🏆 Award

**Excellence Award (우수상)**  
Awarded based on the **average performance across both tasks.**

- **Task 1: Loan Grade Prediction**  
  📊 [Leaderboard](https://www.kaggle.com/competitions/2-ai-loan/leaderboard)

- **Task 2: Diabetes Prediction**  
  📊 [Leaderboard](https://www.kaggle.com/competitions/2-ai/leaderboard)

---

## 🔍 Problem Overview

Both tasks involved **tabular structured data** requiring careful preprocessing and feature design:

1. **Loan grade classification** based on customer financial information  
2. **Diabetes classification** based on medical and demographic data

The key challenge was to maximize performance through **feature engineering, model selection, and ensemble strategies**.

---

## 📦 Baseline

A starter notebook was provided as a baseline. It used a simple `RandomForestClassifier` with minimal preprocessing.

### Limitations of the baseline:
- No missing value handling  
- No feature engineering  
- No hyperparameter tuning  
- Simple train/validation split (no cross-validation)  
- Single model only  

📄 [Baseline Notebook: 고객대출등급 완전 베이스.ipynb](./고객대출등급 완전 베이스.ipynb)

---

## 🧪 Task 1: Loan Grade Prediction

### Experiment Phases
- **Phase 1 (#1–#3):** Basic preprocessing and imputation  
- **Phase 2 (#4–#12):** Feature engineering (e.g., interest burden ratio, employment-to-credit ratio)  
- **Phase 3 (#6–#13):** Model exploration (LightGBM, CatBoost, RF, SVM) → LightGBM + ensemble performed best  
- **Phase 4 (#21–#30):** Feature importance–based selection, stacking/voting  
- **Phase 5 (#31–#47):** Hyperparameter tuning with Optuna; explored interactions  

> **Highlight:** Best results achieved with **LightGBM + feature selection + ensemble voting**

---

## 🧪 Task 2: Diabetes Prediction

### Experiment Phases
- **Phase 1 (#1–#6):** Missing value treatment (domain-driven), initial feature creation  
- **Phase 2 (#7–#13):** Model comparison → LightGBM again performed best  
- **Phase 3 (#14–#20):** Interaction features (e.g., BMI × glucose, Age × HbA1c) → peak Kaggle score **0.811983**  
- **Phase 4 (#21–#40):** Ensemble methods (voting, stacking), SMOTE, class weights, Optuna tuning  

> **Highlight:** Validation F1 peaked at **0.894**, Kaggle best **0.811983**

---

## 🤖 Models Used

| Model        | Usage               | Notes                                   |
|--------------|---------------------|-----------------------------------------|
| LightGBM     | ✅ Main model        | Best overall performance with tuning    |
| CatBoost     | ✅ Secondary model   | Stable results, used in ensembles       |
| XGBoost      | ✅ Final stages      | Helpful in weighted voting ensembles    |
| RandomForest | ✅ Baseline          | Limited improvement beyond baseline     |
| SVM          | ❌ Discarded         | Poor performance on structured data     |

---

## 💡 Key Learnings

- Simple engineered features (e.g., ratios, differences) can strongly boost performance  
- Overly complex pipelines often reduced generalization  
- Ensemble strategies (LightGBM + Optuna-tuned XGBoost/CatBoost) outperformed single models  
- Class imbalance handling (SMOTE, class weights) required careful tuning to avoid overfitting  

---

## 📂 Repository Structure

```bash

scu-loan-prediction/
├── notebooks/
│   ├── 고객대출등급 완전 베이스.ipynb
│   └── 당뇨병 예측 이진분류(베이스라인 코드).ipynb
├── README.md

```

## 📌 Reflections

This project highlighted the importance of **structured experimentation** in tabular ML tasks:

- Begin with simple baselines, then incrementally add preprocessing, features, and models  
- Validate every hypothesis with proper cross-validation instead of relying on leaderboard luck  
- Maintain reproducibility through careful documentation and organized submissions  

Although the original competition notebooks are not fully preserved,  
this archive captures the **workflow, reasoning, and lessons learned** that led to an **Excellence Award**.  

---

## 🔭 Future Work

If revisited, potential improvements include:

- **Explainability**: Applying SHAP or LIME to interpret key drivers of loan grades and diabetes outcomes  
- **AutoML**: Leveraging frameworks like Optuna or FLAML to automate model search and parameter tuning  
- **Feature Store**: Building reusable engineered features for future SCU or Kaggle-style competitions  
- **Robust Imbalance Handling**: Exploring advanced resampling and cost-sensitive learning techniques  
- **Deployment Perspective**: Packaging the final model into a simple API or dashboard for practical use

