## 📅 Submission Summary (2025-08-05)

| No. | Description                                              | Details                                                                                              | SMAPE                  |
|-----|----------------------------------------------------------|------------------------------------------------------------------------------------------------------|------------------------|
| 23  | Weighted Voting + Outlier Smoothing                     | Adjusted VotingRegressor weights to (0.7, 0.2, 0.1) to emphasize XGB, and applied median smoothing to outliers | Local: 11.8013 / LB: **76.8344** |
| 24  | Optuna-Weighted Time × Building Ensemble                | Kept the time × building type segmentation, but optimized voting weights per group using Optuna     | Local: 11.7013 / LB: **9.4649**  |
| 25  | Outlier-Handled Segmented Voting                        | Applied IQR-based outlier filtering on the time × building segmented VotingRegressor to reduce prediction noise | Local: 11.6907 / LB: **15.1169** |
