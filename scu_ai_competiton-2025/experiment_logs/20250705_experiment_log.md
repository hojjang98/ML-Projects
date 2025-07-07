## 🗕️ Experiment Log 🟩 Day 12 (Submissions 56–60)

### 🧪 Summary Table

| Submission | Description | Local AUC | Kaggle AUC |
|------------|-------------|-----------|------------|
| 56 | StackingClassifier with LGBM as meta-model | 0.8617 🔻 | 0.889773 🔻 |
| 57 | Voting (5:3:2) with expanded clustering (behavior + purchase) | 0.8807 🔺 | 0.895620 🔺 |
| 58 | Voting (5:3:2), increased cluster count to 6 | 0.8808 🔸 | 0.894768 🔻 |
| 59 | Voting (5:3:2), removed bottom 10% features by importance | 0.8816 🔺 | 0.895267 🔸 |
| 60 | Voting (5:3:2), added 10+ high-level derived features | 0.8788 🔻 | 0.897255 🔺 (🔥 near best)

---

### 📝 Notes

📊 **Submission 56** tested StackingClassifier again, this time replacing LogisticRegression with LGBM as the meta-model. Unfortunately, while leaderboard AUC was decent, local CV performance dropped, confirming stacking remains unstable.

🧪 **Submission 57** expanded behavioral representation by adding an extra clustering feature (`구매패턴_클러스터`). This significantly stabilized the ensemble, improving both CV and leaderboard scores.

📉 **Submission 58** experimented with increasing cluster granularity (n_clusters=6), but it slightly hurt Kaggle AUC — suggesting over-fragmentation harms performance.

✂️ **Submission 59** used LightGBM importance to prune the bottom 10% of features. Local AUC slightly increased, but leaderboard score was nearly flat, implying many low-importance features still carried marginal signal.

🚀 **Submission 60** introduced a powerful set of interaction features (e.g., `총구매/소득`, `웹방문×소득`, `와인×캠페인`). While CV AUC slightly dipped, **Kaggle AUC surged to 0.897255**, nearly tying the all-time best score.

---

### 🚩 Insights & Next Steps

- ⚠️ **StackingClassifier remains inferior** to VotingClassifier, even with better meta-models like LGBM.
- ✅ **Behavior + Purchase Clustering (n=4)** offers best cluster-based enhancement without overfitting.
- ✅ **High-quality derived features** yield tangible leaderboard gains. Feature engineering > model tweaking.
- ⚠️ **Aggressive pruning (importance or correlation)** has minimal benefit on Kaggle performance.

---

### 🔜 Next Steps for Submission 61+

- ✂️ Try **top-30 feature subset** to test simplified model structure.
- 🧠 Try **Boruta / permutation-based feature selection** for more robust importance filtering.
- 🧩 Try **OneHotEncoding of cluster labels** to capture non-linear boundaries.
- 🧪 Test ensemble of **just LGBM + RF** (drop LR from VotingClassifier).
