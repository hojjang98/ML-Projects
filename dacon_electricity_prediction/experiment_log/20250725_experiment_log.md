## 📅 Submission Summary (2025-07-25)

| No. | Description                                                   | Details                                                                 | SMAPE         |
|-----|---------------------------------------------------------------|-------------------------------------------------------------------------|---------------|
| 13  | Voting Ensemble + Full Feature Expansion                      | Included time, weather, and building features / XGB + LGBM + GBR + Optuna   | **12.38430**  |
| 14  | XGBoost + SelectFromModel Feature Selection                   | Selected only important features using model-based selection / Optuna (n=10) | **11.65735**  |
| 15  | XGBoost + Domain-Specific Features (from Literature)          | Added cumulative averages, season-temperature interactions, etc. / Optuna (n=10) | **11.73231**  |

---

## 🔁 Notes

- **Submission 13**: Maximal feature expansion using domain knowledge with ensemble model; may suffer from feature dilution.
- **Submission 14**: Clean and effective model using only the most important features; achieved the best generalization.
- **Submission 15**: Applied features inspired by academic literature; showed strong performance despite high complexity.

---

## ⏭️ Next Planned Experiments

- Test `SelectFromModel` + **LightGBM**  
- Re-evaluate **Voting/Stacking ensemble** with only top features  
- Train models **per building type** (e.g., hospital, education)  
- Add **lag features** and **rolling averages** for temporal context  
- Explore **recency weighting** to emphasize recent data in training

---
