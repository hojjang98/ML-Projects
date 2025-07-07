## 🗕️ Experiment Log 🟩 Day 13 (Submissions 61–65)

### 🧪 Summary Table

| Submission | Description                                           | Local AUC | Kaggle AUC |
|------------|-------------------------------------------------------|-----------|------------|
| 61         | Voting (6:2:2), slight LGBM emphasis                  | 0.8801    | 0.897686 🔺 (BEST) |
| 62         | Voting (7:2:1), heavier LGBM weighting                | 0.8785    | 0.895581 🔻 |
| 63         | Voting (6:2:2) w/o clustering features                | 0.8818    | 0.895502 🔻 |
| 64         | LGBM only (no Voting), clustering retained            | 0.8759    | 0.888441 🔻 |
| 65         | Voting (6:2:2) + massive new interaction features     | 0.8801    | 0.897686 🔺 (ties best) |

---

### 📝 Notes

📊 **Submission 61** rebalanced the Voting weights to 6:2:2, boosting LGBM's influence. This simple tweak gave the **best overall Kaggle AUC so far (0.897686)**, with stable CV.

📉 **Submission 62** pushed LGBM further with 7:2:1 weights, but the marginal gain wasn’t sustained. Kaggle AUC dropped slightly, suggesting diminishing returns.

✂️ **Submission 63** removed clustering features to validate their utility. Interestingly, CV AUC increased slightly, but Kaggle AUC dropped — indicating clustering helps leaderboard generalization.

🧪 **Submission 64** tested a clean LGBM-only setup. Performance fell on both CV and Kaggle sides, confirming the Voting ensemble's superiority.

🚀 **Submission 65** reintroduced Voting (6:2:2) and added **10+ new derived features** using `고객_최근_캠페인_수락여부`. It matched the best Kaggle AUC again, showing the power of **target-aware feature engineering**.

---

### 🚩 Insights & Next Steps

- ✅ **VotingClassifier (6:2:2)** remains the sweet spot — stable and powerful.
- ✅ **Clustering features help leaderboard generalization**, even if CV gains are minimal.
- ✅ **`고객_최근_캠페인_수락여부`** is a high-impact feature for both standalone use and derived interactions.
- ⚠️ Too much LGBM weighting (7:2:1) doesn’t help; **balance still matters**.
- ⚠️ LGBM-only models underperform consistently.

---

### 🔜 Next Steps for Submission 66+

- 🧪 Test Voting (6:2:2) with **top-40 importance-ranked features** only.
- 🎯 Explore **Boruta, SHAP, or permutation importance** for feature filtering.
- 🧩 Try **Label/OneHot encoding** of cluster labels instead of numeric.
- 🧪 Evaluate Voting (6:4:0) **without LR** to remove redundancy.
- 🧠 Test auto-feature-generation tools (like Featuretools) for discovery.