# 🗕️ Experiment Log  🟪 Day 3 (Submissions 11–15)

## 🧪 Summary Table

| Submission | Description                                                                                    | Local AUC | Kaggle AUC   |
| ---------- | ---------------------------------------------------------------------------------------------- | --------- | ------------ |
| 11 (Best)  | Added **KMeans-based clustering features** (n\_clusters=4) to Optuna-tuned LGBM.               | 0.8695    | **0.897314** |
| 12         | Used more behavior-based features + increased `n_clusters=8` (important features preselected). | 0.8692    | 0.884553     |
| 13         | Same as 11, but only increased `n_clusters=8` (no importance filtering).                       | 0.8706    | 0.892084     |
| 14         | 11-structure + Added **a few interaction features** (income×purchase, web×campaign).           | 0.8735    | 0.892280     |
| 15         | 11-structure + **Added VotingClassifier ensemble** (LGBM, RF, GB) on top.                      | 0.8727    | 0.884915     |

---

## 📝 Notes

* ✅ **Submission 11 remains the overall best**, showing the impact of simple clustering-based feature engineering.
* 📉 Submission 12 showed that **increasing cluster complexity or relying on importance-based feature selection** doesn't always help.
* ⚖️ Submissions 13–15 indicate that the **base LGBM + clustering** is already strong; further changes yielded stable but not improved results.
* 🔁 Interaction features (14) and Voting ensemble (15) provided solid performance but didn't surpass the peak.
* 👉 **Tomorrow’s goal: break the 0.900 AUC mark** by refining the strongest base (11) further — smarter feature interaction, SHAP pruning, or pseudo-labeling could help.
