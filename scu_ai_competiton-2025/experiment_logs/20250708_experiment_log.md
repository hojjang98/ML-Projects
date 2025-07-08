## 🗕️ Experiment Log 🟩 Day 14 (Submissions 66–70)

### 🧪 Summary Table

| Submission | Description                                           | Local AUC | Kaggle AUC |
|------------|-------------------------------------------------------|-----------|------------|
| 66         | Voting (7:1.5:1.5), slightly heavier LGBM weight      | 0.8802    | 0.896619 🔻 |
| 67         | Voting (8:1:1), even more LGBM-heavy                  | 0.8798    | 0.894866 🔻 |
| 68         | Voting (6:2:2), clustering features removed           | 0.8818    | 0.895502 🔻 |
| 69         | LGBM-only + Optuna hyperparameter tuning             | 0.8885    | 0.892163 🔻 |
| 70         | LGBM-only (no tuning) + extensive feature engineering | 0.8828    | 0.879519 🔻 |

---

### 📝 Notes

📊 **Submission 66** tested a slight LGBM weight boost (7:1.5:1.5). Performance remained strong, but fell just below the best.

📉 **Submission 67** pushed LGBM to 8:1:1. This overemphasis slightly hurt performance — confirming that **too much LGBM is suboptimal**.

✂️ **Submission 68** removed both clustering features. CV AUC stayed high, but leaderboard AUC dropped — further proving that **clustering aids generalization**.

🧪 **Submission 69** used Optuna to tune a standalone LGBM model. While CV AUC peaked at **0.8885**, it still couldn’t beat the Voting ensemble on Kaggle.

🧪 **Submission 70** tested a no-tuning, basic `LGBMClassifier()` paired with heavy new feature engineering. CV held up well, but leaderboard AUC declined sharply, showing **feature overload ≠ better generalization**.

---

### 🚩 Insights & Next Steps

- ✅ **Voting (6:2:2)** remains optimal — simple, balanced, and robust.
- ✅ **Clustering adds generalization power**, even if it doesn’t boost CV AUC much.
- ✅ **Optuna can push single models far**, but ensembles still dominate.
- ⚠️ **Too much LGBM weight (7+ out of 10)** reduces ensemble effectiveness.
- ⚠️ **Feature explosion without selection** can actually degrade leaderboard performance.

---

### 🔜 Next Steps for Submission 71+

- 🧪 Test **Voting (6:2:2)** with only **top-40 features** by importance.
- 🧠 Use **SHAP, permutation importance**, or **Boruta** for smarter feature selection.
- 🔀 Try **OneHot encoding** for cluster labels instead of numeric.
- 🎯 Try **Voting (6:4:0)** to **remove LogisticRegression** from the ensemble.
- ⚙️ Explore **automated feature generation tools** (e.g. Featuretools).

