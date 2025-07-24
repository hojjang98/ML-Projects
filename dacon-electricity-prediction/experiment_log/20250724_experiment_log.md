## 📅 Submission Summary (2025-07-24)

| No. | Description                                | Details                                                             | SMAPE         |
|-----|--------------------------------------------|----------------------------------------------------------------------|---------------|
| 10  | Voting Ensemble + 4 New Features + Optuna  | hour_sin, hour_cos, 냉방_x_시간, 면적_x_요일 / Optuna (n=15)         | **11.34327**  |
| 11  | XGBoost Only + Fast Optuna (n=10)          | Same 4 features, minimal tuning time with decent performance         | 11.68912      |
| 12  | XGBoost + 5 Additional Features            | 9 total engineered features → slight overfitting observed            | 13.66468      |

---

## 🔁 Notes

- Submission 10 confirmed strong performance using a small set of derived features and fast tuning.
- Submission 11 proved that even quick tuning can be effective with well-chosen features.
- Submission 12 showed that excessive feature addition may hurt generalization in some models.

---

## ⏭️ Next Planned Experiments

- Explore `StackingRegressor` with tuned base models  
- Segment training by building type (hospital, education, etc.)  
- Add lag features and moving averages to enrich time-series context  
- Consider post-weighting recent samples higher in training loss  
- Revisit feature selection to reduce overfitting in simpler models
