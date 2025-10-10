## 📅 Submission Summary (2025-07-22)

| No. | Description                                | Details                                                             | SMAPE         |
|-----|--------------------------------------------|----------------------------------------------------------------------|---------------|
| 4   | RandomSearchCV tuning (XGBoost)            | Basic feature set, SMAPE optimized with 3-fold CV                   | 17.75976      |
| 5   | Hold-out validation + Feature Engineering  | Date-based split, building + temporal features + Voting Ensemble    | 16.15700      |
| 6   | Optuna tuning + Ensemble                   | Individually tuned XGB/LGBM/GBR via Optuna, then ensembled          | **11.33852**  |

---

## 🔁 Notes

- RandomSearchCV stabilized performance but showed signs of overfitting.
- Submission 5 introduced hold-out validation and time-based features, improving generalization.
- Optuna-based per-model tuning (submission 6) significantly boosted leaderboard performance.

---

## ⏭️ Next Planned Experiments

- Apply StackingRegressor instead of Voting
- Train models per building type (e.g., hospital vs. office)
- Add lag and rolling features to capture temporal trends
- Consider weighting recent data higher in loss calculation
