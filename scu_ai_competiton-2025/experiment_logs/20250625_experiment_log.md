# 🗕️ Experiment Log 🟪 Day 4 (Submissions 16–20)

## 🧪 Summary Table

| Submission | Description                                                                                       | Local AUC | Kaggle AUC   |
| ---------- | ------------------------------------------------------------------------------------------------- | --------- | ------------ |
| 16         | Used **SHAP-based Top 20 feature selection** + Optuna LGBM.                                       | 0.8727    | 0.557659 ❌   |
| 17         | StackingClassifier with **RF, GB, Optuna-tuned LGBM**, final estimator = Optuna LGBM.             | 0.8727    | 0.889753     |
| 18         | Hybrid: 11-structure + **selected interaction features** + **Voting ensemble** (LGBM, RF, GB).    | 0.8699    | 0.884210     |
| 19         | **No Feature Engineering**. Only original features + **Optuna (100 trials) LGBM**.                | 0.8751    | 0.887814     |
| 20         | 19-structure + **only top 5 proven engineered features** (e.g., 와인비율, 총구매, 웹×캠페인 등) 추가. | **0.8789** | 0.884582     |

---

## 📝 Notes

* ❌ **Submission 16 failed** due to SHAP-based feature filtering reducing generalization power (likely over-pruning).
* ✅ Submission 17 showed **solid ensemble performance** with stacking, but didn't surpass previous bests.
* 🧪 Submission 18 was a hybrid attempt, but **adding interaction + voting** didn’t outperform cleaner base models.
* 🥈 **Submission 19 (no feature engineering!) nearly matched ensemble scores**, proving that **Optuna-tuned LGBM** alone is very strong.
* 🔁 Submission 20 added back only **critical engineered features** and saw **local AUC improve**, but **Kaggle AUC slightly dropped** → possible signal overfitting.

---

## 🚩 Insights & Next Steps

* 🧠 **Simple is strong** — removing noise and focusing on pure model capacity proved effective (see 19).
* 🧩 Best-performing additive features may be only a small subset (e.g., 와인비율, 웹×캠페인).
* 🔜 **Submission 21 Goal**: Try **only adding cluster-based features (from 11)** to 19-structure to test whether clustering alone adds generalization value.