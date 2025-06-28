# 📅 Experiment Log 🟦 Day 3 (Submissions 6–10)

## 🧪 Summary Table

| Submission | Description                                                                 | Local AUC | Kaggle AUC |
|------------|------------------------------------------------------------------------------|-----------|------------|
| 6          | Applied `StackingClassifier` with default parameters (no tuning).           | 0.870     | 0.882996   |
| 7          | Tuned RF, GB, and LGBM individually with `RandomizedSearchCV`. Used in stacking. | 0.8693    | 0.877874   |
| 8 (Best)   | Tuned RF, GB, LGBM individually and combined via `VotingClassifier` (soft). | 0.8647    | **0.889646** |
| 9 (Best)   | Used **only** Optuna-tuned `LGBMClassifier` (no ensemble).                  | 0.8695    | **0.895277** |
| 10         | Added multiple interaction features to LGBM model.                          | 0.8741    | 0.885435   |

## 📝 Notes

- Stacking did not outperform voting in this dataset, even with tuned models.
- Surprisingly, **LGBM-only model (no ensemble)** achieved the highest Kaggle AUC (0.8953).
- Feature interaction (10.submission) did not improve performance and may have introduced noise.
- Submission 9 remains the strongest, proving simplicity + good tuning can outperform complex ensembles.
