## 🗕️ Experiment Log 🟪 Day 7 (Submissions 31–35)

### 🧪 Summary Table

| Submission | Description | Local AUC | Kaggle AUC |
|------------|-------------|-----------|------------|
| 31 | Added high-explainability engineered features + selected interactions + Optuna-tuned LGBM + importance plot | 0.8781 | 0.893544 |
| 32 | More aggressive Optuna tuning with higher trial count | 0.9058 🔺 | 0.886189 🔻 |
| 33 | CV-based Optuna tuning to mitigate overfitting | 0.8868 | 0.880841 |
| 34 | Refined 31.submission with automated Optuna tuning + early stopping | 0.8869 | 0.885934 |
| 35 | Simpler model (no Optuna) + reduced low-importance features, pure LGBM | 0.8765 | 0.885464 |

---

### 📝 Notes

📊 **Submission 31** established a strong structure using meaningful features and Optuna-tuned LGBM. It combined selected interaction features and visualized importance, yielding solid generalization.

📈 **Submission 32** aimed for max performance via more intensive Optuna tuning. While it achieved the highest local AUC, Kaggle performance dropped — likely due to overfitting.

🧪 **Submission 33** introduced CV-based tuning to reduce variance. However, local performance did not fully translate to leaderboard gains.

🛠 **Submission 34** retained the structure of 31.submission but integrated full automation: Optuna with early stopping and pruning. The gain was moderate.

🧼 **Submission 35** avoided overfitting by simplifying — no tuning, fewer low-impact features, classic LGBM setup. Interestingly, it performed competitively despite its minimalism.

---

### 🚩 Insights & Next Steps

- ❗ High local AUC from heavy tuning doesn’t guarantee Kaggle improvement — simple setups generalize better.
- ✅ Models with fewer moving parts + focused feature engineering offer more consistent leaderboard gains.
- ❌ Over-tuned models (e.g., 32, 33) showed diminishing returns or overfitting signs.
- 🔜 **Submission 36 Goal**: Go back to clean, classic structure — but maximize useful feature engineering. Keep the model lightweight, tuning minimal, and evaluate only via CV for trustable signals.
