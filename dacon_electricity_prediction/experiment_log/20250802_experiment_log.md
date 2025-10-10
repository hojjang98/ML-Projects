## 📅 Submission Summary (2025-08-02)

| No. | Description                                                       | Details                                                                                     | SMAPE         |
|-----|-------------------------------------------------------------------|---------------------------------------------------------------------------------------------|---------------|
| 19  | Per-Building-Type Model Splitting                                | Separate model per building type; large variance & severe overfitting in smaller groups     | **76.78765**  |
| 20  | Voting (XGB + LGBM + GBR) — Manual Weights                        | Individually tuned base models with fixed weights (0.5, 0.3, 0.2); solid ensemble performance | **12.46738**  |
| 21  | Time-Based Voting (Night / Day / Evening)                        | Split data by hour group and trained separate VotingRegressor for each time block           | **11.23583**  |

---

## 🔁 Notes

- **Submission 19**: Attempted model specialization by building type; failed due to severe overfitting, likely from limited group data.
- **Submission 20**: Applied manual ensemble weights after tuning individual models via Optuna; improved generalization without stacking.
- **Submission 21**: Best-performing submission so far; successfully captured temporal patterns by using time-segmented ensembles.
