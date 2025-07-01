## 🗕️ Experiment Log 🟪 Day 8 (Submissions 36–40)

### 🧪 Summary Table

| Submission | Description | Local AUC | Kaggle AUC |
|------------|-------------|-----------|------------|
| 36 | All meaningful engineered features included + untuned baseline LGBM | 0.8724 | 0.889244 |
| 37 | Same features, but simpler model (lower depth & learning rate) | 0.8719 | 0.893162 🔺 |
| 38 | Replaced LGBM with RandomForestClassifier | 0.8634 🔻 | 0.880528 🔻 |
| 39 | Replaced LGBM with LogisticRegression | 0.8736 | 0.873604 🔻 |
| 40 | LGBM + RandomSearchCV (30 iterations) for full model tuning | 0.8836 🔺 | 0.891497 |

---

### 📝 Notes

📦 **Submission 36** showed that a clean LGBM baseline, when paired with well-crafted features, performs reliably — even without tuning.

📈 **Submission 37** simplified the model further and surprisingly surpassed all previous submissions in Kaggle AUC. This indicates strong alignment between lightweight structure and the underlying signal in the data.

🌲 **Submission 38** tested RandomForest but fell short. Despite its robustness, it failed to generalize as well as the gradient boosting counterpart.

📉 **Submission 39** used LogisticRegression for interpretability, but it underperformed in leaderboard score — likely due to its limited capacity for modeling nonlinearity or interaction terms.

🧪 **Submission 40** performed full RandomSearchCV-based LGBM tuning. While it improved local AUC significantly, the Kaggle score slightly trailed 37.submission, suggesting that complexity does not always translate to generalization gains.

---

### 🚩 Insights & Next Steps

- ✅ A simpler model (like in **37.submission**) can outperform complex ones when the feature engineering is strong and the problem is well-posed.
- ❌ Alternative models like RF or LR showed limitations under current features.
- 🔁 LGBM remains the most robust choice; further diversity in seed or feature representation might yield additional improvements.
- 🔜 **Submission 41 Goal**: Try VotingClassifier using multiple LGBM variants trained on different seeds or CV splits. Focus on **ensemble stability** rather than model complexity.
