## 📊 Experiment Log — Electricity Usage Forecasting (36–43)

| No. | Description | Local SMAPE | Public LB SMAPE |
|-----|-------------|-------------|-----------------|
| 36  | Split data by building type, tuned **XGBoost** and **LightGBM** via `RandomizedSearchCV`, applied **7-Fold OOF CV**, and blended predictions using optimal weights from OOF results. *(best)* | 3.982886 | **7.1161849075** |
| 37  | Extended Exp. 36 with **RepeatedKFold** for variance reduction, refined OOF-based weight search to 0.01 increments, and retrained each optimal model with multiple seeds for **seed averaging**. | 3.982668 | **7.0759340681** |
| 38  | Computed **fold-wise optimal weights**, blended using the **average of these weights**, and applied 5-seed averaging for further variance reduction. | — | — |
| 39  | Addressed overfitting from best score: tuned XGB/LGBM per building type with RS-CV, computed **fold-wise optimal weights** on 7-Fold OOF, averaged them, and retrained with **5 seeds** for seed averaging. *(best)* | 4.065438 | **7.0021252141** |
| 40  | Implemented an “overfitting-mitigation” unified code: flexible folds, negative prediction clipping, standardized LGBM parameters, adaptive weight shrinkage, 5-seed averaging, and enhanced logging. | 4.370971 | **7.0118167688** |
| 41  | Tuned XGB/LGBM with RS-CV per building type, then blended fold-wise optimal weights using **trimmed mean + shrink**, combined with 5-seed averaging for more stability. | 12.496758 | **6.9964770263** |
| 42  | Partitioned by building type, tuned XGB/LGBM with **light RS-CV (n_iter=6)**, blended weights with trimmed mean + shrink, and applied **3-seed averaging + post-processing** (0/top clipping, building-level median filter, OOF bias correction). | 12.553428 | **15.1738844787** |
| 43  | Single-model XGB per building type, tuned with RS-CV (*n_iter=8*), validated with **TimeSeriesSplit(7)** OOF, applied 5-seed averaging + building-level median filtering. Disabled bias/top clipping for leaderboard stability. | 16.282731 | **7.1981428039** |

**Best Score:** 🏆 **7.0021252141** (Experiment 39, Public LB)
