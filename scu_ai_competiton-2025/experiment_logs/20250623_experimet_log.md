# 📅 Experiment Log 🟨 Day 1 (Submissions 1–5)

## 🧪 Summary Table

| Submission | Description                                                             | Local AUC | Kaggle AUC |
|------------|--------------------------------------------------------------------------|-----------|------------|
| 1          | Baseline model submitted without any modifications.                     | 0.878     | 0.878892   |
| 2          | Replaced missing values in `Income` with mean. Applied VotingClassifier. | 0.860     | 0.884367   |
| 3          | Added `RandomizedSearchCV` for hyperparameter tuning.                   | 0.863     | 0.887256   |
| 4          | Switched to `Optuna` for more efficient tuning.                         | 0.876     | 0.887677   |
| 5 (Best)   | Optuna-tuned `LGBMClassifier` in VotingClassifier ensemble.              | 0.862     | **0.889225** |

## 📝 Notes

- **VotingClassifier** showed notable gains from submission 2 onward.
- **Optuna** outperformed RandomizedSearchCV in both local and Kaggle scores.
- Submission 5 was the best combination so far.
- Slight dip in local AUC for submission 5 may suggest minor overfitting or variance.
