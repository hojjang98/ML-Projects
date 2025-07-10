## 🗕️ Experiment Log 🟩 Day 16 (Submissions 76–80)

### 🧪 Summary Table

| Submission | Description                                                    | Local AUC | Kaggle AUC |
|------------|----------------------------------------------------------------|-----------|------------|
| 76         | Voting (6:2:2) + Cluster **Distance** Features (KMeans)        | 0.8747    | 0.890322 🔻 |
| 77         | LGBM **single model only** + GridSearchCV                      | 0.8767    | 0.890155 🔻 |
| 78         | Voting (6:2:2) + Explosive Derived Features                    | 0.8864    | 0.893553 🔼 |
| 79         | Top-50 features by LGBM importance only                        | 0.8879    | 0.893269 🔼 |
| 80         | All features minus those with **zero importance**             | 0.8881    | 0.894582 🔼 |

---

### 📝 Notes

📉 **Submission 76** tested KMeans cluster center **distance-based features**. While intuitive, these features added noise and slightly lowered both CV and leaderboard AUC.

🔂 **Submission 77** reverted to a **pure LGBMClassifier** (no Voting), with exhaustive GridSearchCV tuning. Results were stable but failed to beat ensemble-based submissions.

💥 **Submission 78** returned to the best-performing ensemble (Voting 6:2:2) and added a **large number of interaction/ratio-based features**. Strong CV performance and decent leaderboard score.

🧪 **Submission 79** filtered the features to **top 50** based on LGBM importance. AUC dropped slightly on leaderboard, but the result was highly interpretable and lightweight.

🧼 **Submission 80** smartly retained all features **except those with zero importance**. This light cleanup improved leaderboard performance slightly while preserving model richness.

---

### 🚩 Insights & Learnings

- ✅ Distance to cluster centers often **adds noise** rather than meaningful structure.
- ✅ Simple **LGBM-only models** are reliable, but lack the synergy of Voting ensembles.
- ✅ **Explosive feature engineering** still adds value when properly balanced.
- ✅ **Feature pruning** (importance-based) is helpful, but removing too much (like in 79) may cut off subtle interactions.
- ✅ Best balance so far: Voting (6:2:2) + all useful derived features – zero-importance features removed.

---

### 🔜 Next Steps for Submission 81+

- 📌 Try **top N important features + manually selected cluster features**.
- 🧠 Build **interaction features from top 10 important variables only**.
- 🔎 Use **SHAP values** for more robust feature selection.
- 🔁 Tune **Voting weights** again (e.g., 7:2:1 or 5:3:2 revisited).
- 🎯 Use **feature importances from ensemble meta-models** for future filtering.
