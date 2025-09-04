# 🚢 Titanic - Predicting Survival with Machine Learning

> *My very first Kaggle-style ML project.*  
This project was an entry point into machine learning competitions — a simple but iconic challenge to predict survival on the Titanic.  
Since it was beginner-friendly, I wrapped it up fairly quickly, but it helped me learn the full workflow from EDA to submission.

---

## 🎯 Objectives
- Practice a complete **Kaggle pipeline** (EDA → feature engineering → modeling → submission)  
- Explore different ML models and ensemble strategies  
- Learn how validation and Kaggle leaderboard scores can differ  
- Build confidence before moving on to more complex projects  

---

## 📁 Project Structure

```bash

titanic-survival-prediction/
├── data/                # Raw and processed datasets (not included)
├── figures/             # Visualizations (EDA, feature importance, etc.)
├── notebooks/           # Jupyter notebooks (EDA, modeling, final submission)
├── submissions/         # Kaggle submissions + log
│   ├── submission_log.md
│   ├── final_submission.csv
│   └── submission_v*.csv
├── requirements.txt     # Dependencies
├── .gitignore           # Ignore rules
└── README.md            # Project overview

```

---

## 🧪 Experiments & Results

| # | Model / Method | Validation Acc | Kaggle Score |
|---|----------------|----------------|--------------|
| 1 | VotingClassifier (RF, GBM, XGB, soft) | 0.8090 | 0.77751 |
| 2 | StackingClassifier (LR meta) | 0.8034 | 0.77511 |
| 3 | CatBoostClassifier | 0.7753 | 0.76315 |
| 4 | Soft Voting + GridSearchCV | 0.7921 | **0.77990** |
| 5 | RandomForest + Optuna tuning | 0.8146 | 0.77511 |
| 6-8 | Feature Selection + Voting (GridSearchCV) | 0.8146 | 0.76555 |

**Best Kaggle Score**: `0.77990` (Soft VotingClassifier with GridSearchCV)  
**Best Validation Accuracy**: `0.8146` (Optuna-tuned RandomForest)  

---

## 📊 What I Learned
- Ensemble methods (Voting, Stacking) generally outperformed single models.  
- Optuna gave the best validation accuracy, but not the best leaderboard score — **validation ≠ Kaggle performance**.  
- Feature selection sometimes didn’t help; in fact, it could hurt.  
- Submitting multiple times and tracking results in `submission_log.md` kept the workflow organized.  

---

## ⚡ Reflections
This project was **quick and manageable** — perfect as a first step.  
It helped me practice the full ML competition cycle, and now I feel ready to tackle **bigger, messier datasets** where creativity and stronger pipelines matter.  

---

## ✍️ Author
Made with curiosity by [hojjang98](https://github.com/hojjang98)  
*First project complete. On to the next one!* 🚀

