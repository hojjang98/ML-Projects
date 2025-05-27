# 🚢 Titanic - Predicting Survival with Machine Learning

Welcome aboard!  
This project is a hands-on machine learning exploration using the famous Titanic dataset from Kaggle.  
It’s basically the “Hello, World!” of data science — and here I am, diving in.

---

## 🎯 What I'm Trying to Do

- Explore the dataset (EDA)
- Make sense of the features and do some feature engineering
- Train machine learning models (coming soon!)
- Create and submit predictions to Kaggle
- Learn and have fun while building my data science workflow

---

## 📁 Project Structure

```
titanic-survival-prediction/
├── data/                  
│   ├── train.csv
│   ├── test.csv
│   ├── train_processed.csv
│   └── test_processed.csv
│
├── notebooks/             
│   ├── 01_EDA.ipynb
│   ├── 02_Modeling.ipynb
│   └── 03_Final_Submission.ipynb
│
├── figures/              
│   ├── Survival_Count.png
│   ├── Age_Distribution.png
│   └── ... (etc.)
│
├── submissions/           
│   ├── submission_v1_soft_voting.csv
│   ├── submission_v2_stacking.csv
│   ├── ...
│   └── submission_log.md
│
├── scripts/              
├── models/                
│
├── requirements.txt       
├── README.md              
└── .gitignore            
```

---

## 🛠️ Tech Stack

- Python 3.10.1  
- pandas & numpy  
- matplotlib & seaborn  
- scikit-learn  
- xgboost  
- catboost  
- optuna  
- missingno

---

## 📝 Progress Log

> This section will be updated as the project grows!

- [x] EDA ➡️ [01_EDA.ipynb](./notebooks/01_EDA.ipynb)  
- [x] Feature Engineering  
- [x] Modeling ➡️ [02_Modeling.ipynb](./notebooks/02_Modeling.ipynb)  
- [x] Kaggle Submission ➡️ [03_Final_Submission.ipynb](./notebooks/03_Final_Submission.ipynb)

---

## 📈 Project Workflow

Here’s how I actually worked through the Titanic survival prediction project:

1. **EDA (Exploratory Data Analysis)**  
   - Used `seaborn`, `missingno`, `matplotlib` to visualize survival by `Sex`, `Pclass`, and `Age`  
   - Checked missing values and handled `Cabin`, `Embarked`, `Age`, and `Fare`  
   - Explored feature relationships (e.g., `FamilySize`, `IsAlone`, `Title`) to prepare for modeling

2. **Feature Engineering**  
   - Extracted titles from the `Name` column (Mr, Mrs, Miss, etc.)  
   - Created `FamilySize`, `IsAlone`, `CabinFlag` as new features  
   - Encoded `Sex` and `Title` using `LabelEncoder`  
   - Dropped or transformed less useful columns like `Cabin`, `Ticket`

3. **Modeling**  
   - Trained multiple models: RandomForest, GradientBoosting, XGBoost, CatBoost  
   - Tuned hyperparameters using `GridSearchCV` and `Optuna`  
   - Built ensemble models:  
     - **Soft VotingClassifier** using RF, GB, XGB  
     - **StackingClassifier** with Logistic Regression as meta-model  
   - Applied feature selection using `SelectFromModel` (RandomForest 기준)

4. **Evaluation & Submission**  
   - Compared models using validation accuracy and Kaggle score  
   - Best validation accuracy: **0.8146** (Optuna-tuned RF, VotingClassifier with feature selection)  
   - Best Kaggle public score: **0.77990** (VotingClassifier with GridSearchCV tuning)  
   - Saved and submitted predictions multiple times, with results tracked in `submission_log.md`

5. **Wrap-up**  
   - Cleaned up the project structure and notebooks  
   - Saved key visualizations to `figures/` folder  
   - Organized submissions, tracked model performance, and documented everything here  
   - Ready to apply this full pipeline to a bigger, messier dataset next!


## 🤓 Notes to Self

- Keep code clean and modular
- Try different models and compare results
- Don’t be afraid to mess up — it’s all part of the game


---

## 📚 What I Learned

- Ensemble methods like Voting and Stacking tend to outperform individual models
- Optuna tuning led to the highest validation accuracy, but not the best Kaggle score — lesson learned!
- Validation performance doesn't guarantee leaderboard success → avoid overfitting!
- Feature Selection with `SelectFromModel` didn’t always help (sometimes neutral or worse on leaderboard)
- Submitting with clean, reproducible notebooks helps keep the workflow maintainable

---

## ⚠️ Limitations & Next Steps

- Didn't yet explore SHAP values or permutation-based feature importance  
- No pipeline automation or full script conversion — something to do in the next iteration  
- Feature engineering followed mostly common practices; more creativity possible  
- Kaggle test set is limited in feedback → private score may differ  
- Plan to apply similar workflow to a more complex, real-world dataset next

---


## ✍️ Author

Made with curiosity by [hojjang98](https://github.com/hojjang98)  
Feel free to clone, fork, or just take a peek 😄
