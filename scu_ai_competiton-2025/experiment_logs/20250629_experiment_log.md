## 🗕️ Experiment Log 🟪 Day 6 (Submissions 26–30)

### 🧪 Summary Table

| Submission | Description | Local AUC | Kaggle AUC |
|------------|-------------|-----------|------------|
| 26 | `model_11` and `model_9` tuned with RandomSearchCV and ensembled via soft voting (weights 7:3) | 0.8739 | 0.891203 |
| 27 | `model_11`, `model_9`, `model_21` each tuned with 3 different seeds, ensembled via weighted voting (5:3:2) | 0.8671 | 0.890557 |
| 28 | OOF-based StackingClassifier: meta-features from OOF predictions of 11, 9, 21 → trained with LGBM meta-model | 0.9995 ❗ | 0.836320 ❌ |
| 29 | Back to classic model: removed complex encodings, used only high-explainability features | 0.8460 | 0.873702 |
| 30 | Feature engineering using key variables → added meaningful interaction features | 0.8748 | 0.896824 ✅ |

---

### 📝 Notes

🧪 **Submission 26** used individually tuned models with RandomSearchCV (model_11 and model_9), and the 7:3 weighted soft voting ensemble delivered strong performance on Kaggle.

🔁 **Submission 27** tested whether multiple seeds add robustness. VotingClassifier with 3 seed-tuned models showed slight drop — minimal gain from seed diversity.

❌ **Submission 28** leveraged out-of-fold (OOF) predictions for stacking, but the meta-model overfitted the training data. Local AUC was unrealistically high (0.999), while Kaggle AUC dropped significantly to 0.836.

🧼 **Submission 29** simplified the structure by eliminating redundant categorical encodings and focusing on interpretable features. It delivered a solid baseline despite reduced complexity.

✅ **Submission 30** incorporated targeted feature engineering using only important variables. Resulted in high generalization — nearly reached the competition’s top performance so far.

---

### 🚩 Insights & Next Steps

- ❗ Over-complex ensemble (e.g., stacking with OOF meta-features) led to overfitting and poor generalization.
- ✅ Simpler models with well-engineered features are more reliable and generalize better on unseen data.
- 🔁 Ensemble strategies should only be used when base models have sufficiently diverse error patterns.
- 🔜 **Submission 31 Goal**: Maintain the classic, clean structure; further refine interaction features and add meta-level combinations based on top feature importance.

