## 📅 Submission Summary (2025-08-03)

| No. | Description                                                    | Details                                                                                         | SMAPE         |
|-----|----------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------|
| 22  | Time × Building Type Ensemble (VotingRegressor)               | Split by both time (Night/Day/Evening) and building type (Top 7 + Others); strong local tuning   | **9.61451**   |

---

## 🔁 Notes

- **Submission 22**: Combined segmentation by time and building type to reflect more realistic consumption patterns.  
  Introduced crossed features (e.g., `냉방_x_시간`, `면적_x_요일`) and cyclic time encoding (`hour_sin`, `hour_cos`).  
  Achieved **best leaderboard score** to date with improved precision on segmented patterns.
