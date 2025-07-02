## 🗕️ Experiment Log 🟪 Day 9 (Submissions 41–45)

### 🧪 Summary Table

| Submission | Description | Local AUC | Kaggle AUC |
|------------|-------------|-----------|------------|
| 41 | VotingClassifier – 3 LGBMs with different SEEDs | 0.8749 🔻 | 0.883270 🔻 |
| 42 | VotingClassifier – 3 LGBMs with feature variation (Top 20, 30, All) | 0.8736 🔻 | 0.882673 🔻 |
| 43 | Removed all cluster features from strong baseline | 0.8877 🔺 | 0.890243 |
| 44 | Added 12 high-level engineered features (ratios, interaction, difference) | 0.8801 | 0.894386 🔺 |
| 45 | Added log1p + ratio + delta + nested interactions (Mad Scientist ver.) | 0.8835 | 0.890224 🔻 |

---

### 📝 Notes

🧪 **Submission 41** attempted to stabilize prediction via SEED-based VotingClassifier (3 models). However, due to structural similarity between models, the ensemble added little value.

🔁 **Submission 42** varied feature subsets (Top 20, 30, All) across models in the ensemble, but still couldn’t overcome the redundancy in model structure — result was almost identical to 41.

✂️ **Submission 43** removed all cluster features. Surprisingly, the performance improved, indicating that clustering might have introduced noise rather than structure.

🚀 **Submission 44** embraced expressive feature engineering — adding advanced ratios, deltas, and behavioral interactions. This submission yielded the **best Kaggle score so far**, despite a relatively simple model.

⚗️ **Submission 45** pushed the limit of engineering with `log1p`, ratio-delta stacking, and complex nested combinations. While local AUC stayed strong, Kaggle performance dropped — indicating potential overfitting or signal dilution due to feature overload.

---

### 🚩 Insights & Next Steps

- ✅ Ensembles do not guarantee improvement when model diversity is insufficient (41–42).
- ✅ Removing misleading features like clusters can enhance model generalization (43).
- 🔥 Carefully crafted, interpretable features are more valuable than brute-force mathematical complexity (44 > 45).
- ⚠️ log1p transformations are not always beneficial for tree-based models.
- 🔜 **Submission 46 Goal**: Return to 44.submission feature set and remove noisy log1p/stacked terms. Possibly test SHAP, importance-based selection, or light feature pruning to refine performance further.
