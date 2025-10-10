## 📊 Experiment Log — Electricity Usage Forecasting

| No. | Description                                                                                     | Local SMAPE     | Public LB SMAPE  |
|-----|-------------------------------------------------------------------------------------------------|------------------|-------------------|
| 25  | Applied **IQR-based outlier correction** to VotingRegressor outputs (Time × Building Type)     | 11.6907          | 15.1169           |
| 26  | Added **nonlinear interaction features** (e.g., Season × BuildingType, Temp × Area, etc.)      | ??               | 15.0829           |
| 27  | Selected **Top 20 features** by importance and used them in segmented VotingRegressor           | 11.78283      | 15.2243351317       |
