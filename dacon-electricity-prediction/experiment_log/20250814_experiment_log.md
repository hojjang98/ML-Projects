## 📊 Experiment Log — Electricity Usage Forecasting (36–38)

| No. | Description | Local SMAPE | Public LB SMAPE |
|-----|-------------|-------------|-----------------|
| 36  | Split data by building type, tuned **XGBoost** and **LightGBM** via `RandomizedSearchCV`, applied **7-Fold OOF CV**, and blended predictions using optimal weights from OOF results. *(best)* | 3.982886 | **7.1161849075** |
| 37  | Based on Exp. 36, extended to **RepeatedKFold** for variance reduction, refined OOF-based weight search to 0.01 increments, and retrained each optimal model with multiple seeds for **seed averaging** to reduce overfitting. | 3.982668 | **7.0759340681** |
| 38  | Computed **fold-wise optimal weights**, blended using the **average of these weights**, and applied 5-seed averaging for further variance reduction. Preprocessing remained unchanged. | — | — |

**Best Score:** 🏆 **7.0759340681** (Experiment 37, Public LB)
