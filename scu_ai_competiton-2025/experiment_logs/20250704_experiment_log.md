## 🗕️ Experiment Log 🟩 Day 11 (Submissions 51–55)

### 🧪 Summary Table

| Submission | Description | Local AUC | Kaggle AUC |
|------------|-------------|-----------|------------|
| 51 | Voting (LGBM:RF:LR = 7:2:1), removed 3 extra features added in submission 50 | 0.8833 🔺 | 0.894964 🔻 |
| 52 | LGBM single model, same features, no hyperparameter tuning | 0.8798 🔻 | 0.887903 🔻 |
| 53 | Voting (5:3:2), removed bottom 10% features by importance | 0.8828 🔻 | 0.895062 🔻 |
| 54 | Voting (5:3:2), removed highly correlated features (threshold = 0.95) | 0.8835 🔺 | 0.894983 🔻 |
| 55 | SEED variation tested (42, 84, 123, etc.) → 42 was still best, so converted to StackingClassifier | 0.8780 🔻 | 0.884054 🔻 |

---

### 📝 Notes

🎛 **Submission 51** increased the influence of LGBM in the voting ensemble (7:2:1) and removed the three experimental features from submission 50. Local AUC slightly improved, but Kaggle score dropped, suggesting overfitting to LGBM.

📉 **Submission 52** returned to a single LGBM model with no tuning. Performance was clearly inferior to ensemble models on both local and leaderboard scores.

✂️ **Submission 53** used LightGBM feature importance to drop the bottom 10% of features. This simplified feature space helped stabilize the model locally, but did not translate to gains on Kaggle.

🧩 **Submission 54** removed redundant features using a correlation threshold (0.95). This improved local AUC marginally, but Kaggle AUC remained flat — showing redundancy wasn’t a major issue.

🧱 **Submission 55** tested SEED variation — but SEED=42 (default) already yielded the best CV. The experiment then pivoted to a StackingClassifier. Unfortunately, the stacking structure underperformed compared to voting, both locally and on the leaderboard.

---

### 🚩 Insights & Next Steps

- ✅ Weighting LGBM more heavily can increase local AUC, but may hurt generalization.
- ✅ Feature importance and correlation pruning helps local training but not necessarily leaderboard performance.
- ⚠️ StackingClassifier (with LogisticRegression as meta-model) failed to beat the simpler VotingClassifier.
- ✅ Ensemble models are still best — especially when balanced and tuned.

---

### 🔜 Next Steps for Submission 56+

- 🔄 Try **StackingClassifier again** with **LGBM as the meta-model** (instead of LogisticRegression)
- 🔍 Test **simplified or top-K feature sets** (e.g., top 25 based on importance)
- ⚙️ Explore **n_clusters tuning** in behavioral clustering
- 🧪 Compare soft-voting with just LGBM + RF (drop LR)
