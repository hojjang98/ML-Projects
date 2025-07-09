## 🗕️ Experiment Log 🟩 Day 15 (Submissions 71–75)

### 🧪 Summary Table

| Submission | Description                                                   | Local AUC | Kaggle AUC |
|------------|---------------------------------------------------------------|-----------|------------|
| 71         | Voting (6:2:2) + Full Derived Features + All 4 Clusters       | 0.8793    | 0.899048 🔼 |
| 72         | Same as 71 but increased cluster count for higher granularity | 0.8796    | 0.897295 🔻 |
| 73         | LGBM-only RandomSearch tuning + Voting (6:2:2) ensemble       | 0.8807    | 0.900233 ⬆️ |
| 74         | Explosive Feature Engineering applied                         | 0.8866    | 0.896403 🔻 |
| 75         | Same as 73 but cluster count refined (optimized per type)     | 0.8818    | 0.897902 🔻 |

---

### 📝 Notes

🔀 **Submission 71** combined the full set of engineered features with four distinct cluster features and standard VotingClassifier (6:2:2). Strong generalization on both CV and Kaggle.

📈 **Submission 72** increased the number of clusters in all four types (behavior, purchase, income, time), aiming for finer granularity. Slight AUC gain on CV but slight drop on leaderboard, suggesting **more clusters ≠ better**.

🧪 **Submission 73** tuned only the LGBM using RandomizedSearchCV and combined it in Voting (6:2:2). This setup achieved the **first Kaggle AUC > 0.900**, proving that even lightweight tuning helps.

💥 **Submission 74** added a large number of new interaction & ratio features (explosive feature engineering). While CV improved, leaderboard score declined — possibly due to **overfitting or noise**.

🎯 **Submission 75** reverted to a leaner setup like 73 but optimized the number of clusters using domain knowledge. It balanced performance well, but didn’t outperform submission 73.

---

### 🚩 Insights & Next Steps

- ✅ **LGBM tuning + Voting (6:2:2)** still yields the best overall results.
- ✅ **Cluster-based features are most helpful when carefully tuned (2~5 clusters)**.
- ⚠️ **Over-engineering features** without clear signal hurts leaderboard performance.
- ⚠️ **More clusters ≠ better generalization** — smaller, interpretable clusters work better.
- ✅ Lightweight **RandomSearchCV** provides a sweet spot between speed and performance.

---

### 🔜 Next Steps for Submission 76+

- 🧪 Try **Voting (6:2:2)** with **top-N features** only (e.g. top-40 by importance).
- 📊 Use **SHAP values or permutation importance** for better feature selection.
- 🔄 Test **OneHot encoding of cluster labels** instead of ordinal integers.
- 🧼 Evaluate **noise filtering strategies** (e.g. remove least important 10% features).
- 🛠️ Consider testing **LGBM + RF only (Voting 6:4:0)** ensemble without LR.
