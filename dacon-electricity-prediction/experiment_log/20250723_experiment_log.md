## 📅 Submission Summary (2025-07-23)

| No. | Description                                      | Details                                                                 | SMAPE         |
|-----|--------------------------------------------------|-------------------------------------------------------------------------|---------------|
| 7   | Optuna-Weighted Voting Ensemble                  | Voting weights optimized via Optuna; early stopping at SMAPE < 13.0     | 14.73364      |
| 8   | LGBM Only + RandomSearchCV                       | Tested hypothesis: single model may outperform ensemble                 | 21.60964      |
| 9   | StackingRegressor + Leakage-Free Features        | Ratio + interaction features, stack ensemble instead of voting          | 45.28836      |

---

## 🔁 Notes

- Submission 7 used Optuna not just for tuning each model, but also for **weighting in the Voting ensemble**, yielding solid leaderboard results.
- Submission 8 evaluated a **single well-tuned LGBM**, but confirmed ensemble superiority in this context.
- Submission 9 attempted to **upgrade the ensemble strategy** using StackingRegressor and feature engineering, but suffered from major overfitting—possibly due to poor generalization in meta-model or feature interactions.

---

## ⏭️ Next Planned Experiments

- Re-evaluate feature set used in stacking (reduce dimensionality or collinearity)  
- Add meta-feature smoothing or L2 regularization in stacking  
- Consider time-series split within stacking folds to preserve temporal structure  
- Run ablation study: which engineered features contribute most to SMAPE drop  
- Possibly hybridize stacking + weighted voting if performance diverges by building type
