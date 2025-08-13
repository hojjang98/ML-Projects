## 📊 Experiment Log — Electricity Usage Forecasting (34–35)

| No. | Description | Local SMAPE | Public LB SMAPE |
|-----|-------------|-------------|-----------------|
| 34  | Reduced overfitting by adjusting parameters: `eta`, `subsample`, `colsample_bytree`, `min_child_weight`, `gamma`, `reg_alpha`, `reg_lambda`. | 4.618441972505276 | **7.3385022051** |
| 35  | Split data by building type, optimized **XGBoost hyperparameters** via `RandomizedSearchCV`, applied **7-Fold OOF CV**, then fixed once for stable performance evaluation. | 4.057732 | 7.3767868422 |

**Best Score:** 🏆 **7.3385022051** (Experiment 34, Public LB)
