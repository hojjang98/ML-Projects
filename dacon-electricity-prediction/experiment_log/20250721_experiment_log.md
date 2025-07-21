# 🧪 Experiment Log - DACON Electricity Usage Prediction

This log tracks all submission experiments and their performance (RMSE).  
The goal is to iteratively improve model accuracy through feature engineering and model tuning.

---

## 📅 Submission Summary (2025-07-21)

| No. | Description                          | Details                             | RMSE          |
|-----|--------------------------------------|-------------------------------------|---------------|
| 1   | Sample submission (default)          | All zero predictions                | 200.00000     |
| 2   | Baseline model                       | XGBoost, no building info merged    | 19.49000      |
| 3   | Baseline + building_info merged      | Simple merge, no feature tuning     | 18.60073      |

---

## 🔁 Notes

- All experiments used `XGBRegressor` with default or basic parameters.
- `building_info.csv` merge showed significant improvement (~0.89 drop in RMSE).
- Feature engineering and model tuning (RandomSearch) to be tested in the next batch.

---

## ⏭️ Next Planned Experiments

- Run RandomizedSearchCV for XGBoost with aligned features
- Add temporal features (lag, rolling stats)
- Try LightGBM baseline and tuned versions
