## 📅 Submission Summary (2025-08-01)

| No. | Description                                                       | Details                                                                 | SMAPE         |
|-----|-------------------------------------------------------------------|-------------------------------------------------------------------------|---------------|
| 16  | Voting (XGB + LGBM) — Basic Equal Weights                         | Fast and efficient model with time/building/weather features            | **14.66498**  |
| 17  | Voting (XGB + LGBM) — Manual Weight Tuning                        | Weights set to (0.6, 0.4) based on relative model strength              | **14.61085**  |
| 18  | Voting (XGB + LGBM) — Optuna-Based Weight Optimization            | Auto-tuned weights using Optuna (`xgb_weight ≈ 0.71`)                   | **14.55016**  |

---

## 🔁 Notes

- **Submission 16**: A fast baseline ensemble using equal weights; good balance of speed and performance.
- **Submission 17**: Manually adjusted weights improved results slightly, confirming the stronger contribution from XGBoost.
- **Submission 18**: Automatically optimized weights via Optuna yielded the best ensemble so far; confirms weight tuning effectiveness.
