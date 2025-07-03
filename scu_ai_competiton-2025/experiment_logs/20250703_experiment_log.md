## 🗕️ Experiment Log 🟩 Day 10 (Submissions 46–50)

### 🧪 Summary Table

| Submission | Description | Local AUC | Kaggle AUC |
|------------|-------------|-----------|------------|
| 46 | Removed all `log1p` features, reintroduced both cluster features | 0.8859 🔺 | 0.886561 🔻 |
| 47 | Removed "purchase power cluster", retained only behavioral cluster | 0.8853 🔻 | 0.890586 🔺 |
| 48 | Soft Voting (LGBM + RF + LR) based on 47’s features | 0.8826 🔻 | 0.895777 🔺 |
| 49 | Same Voting setup with weights (LGBM:RF:LR = 5:3:2) | 0.8826 | **0.896188 🔺** |
| 50 | Same Voting (5:3:2) + 3 new features (`high_income_binary`, `recent_purchase_binary`, `combined_ratio`) | 0.8789 🔻 | 0.895855 🔻 |

---

### 📝 Notes

🔍 **Submission 46** verified that `log1p` features had *zero contribution*. Including both clusters improved local AUC but hurt generalization slightly.

🎯 **Submission 47** removed the less effective "purchase power cluster", keeping only the behavioral cluster. This led to a more balanced improvement, especially on Kaggle.

🤝 **Submission 48** introduced a soft voting ensemble (LGBM + RF + LR). While local AUC dropped slightly, generalization improved significantly — diversity in models proved effective.

⚖️ **Submission 49** kept the same ensemble and added tuned weights (5:3:2). This small tweak led to the **second-best Kaggle AUC overall**, confirming LGBM’s key role.

🔬 **Submission 50** added 3 extra features to the same voting setup. Kaggle AUC remained strong, but local AUC declined — likely due to **feature redundancy or noise**.

---

### 🚩 Insights & Next Steps

- ✅ `log1p` transformations are unnecessary for tree-based models like LGBM.
- ✅ Behavioral clustering is useful; **purchase-based clusters may introduce noise**.
- ✅ Ensemble methods work best with **diverse, well-balanced models**.
- ⚠️ Even interpretable features can degrade performance if they create redundancy.
- 🔜 **Next Steps for Submission 51+**:
  - Explore different `random_state` values (SEED variation)
  - Use SHAP or permutation-based feature selection
  - Test CV stability across folds
  - Try simplifying the ensemble (e.g., LGBM + RF only)
