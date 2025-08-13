## 📊 Experiment Log — Electricity Usage Forecasting (32–34)

| No. | Description | Local SMAPE | Public LB SMAPE |
| --- | ----------- | ----------- | ---------------- |
| 32  | Split data by building type, trained a **custom XGBoost model per type** with **7-Fold CV + early stopping**, averaged fold predictions for test set SMAPE eval. | 88.7987 | 87.4434637692 |
| 33  | **Fixed index alignment bug** from Exp. 32 → ensured correct order matching between predictions and ground truth, improved local SMAPE calculation & submission. | **3.315575011287449** | **7.3537720535** |
| 34  | Reduced overfitting by adjusting parameters: `eta`, `subsample`, `colsample_bytree`, `min_child_weight`, `gamma`, `reg_alpha`, `reg_lambda`. | 4.618441972505276 | — (Pending) |

**Best Score:** 🏆 **7.3537720535** (Experiment 33, Public LB)
