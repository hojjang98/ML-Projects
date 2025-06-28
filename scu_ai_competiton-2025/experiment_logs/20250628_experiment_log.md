🗕️ Experiment Log 🟪 Day 5 (Submissions 21–25)
🧪 Summary Table
Submission	Description	Local AUC	Kaggle AUC
21	Built on 11.submission structure, with deeper Optuna tuning (100 trials, CV=10).	0.8795	0.891722
22	Removed unhelpful features, added auto-generated features based on importance.	0.8859	0.878383 ❌
23	Simplified version of 11 with key features + Optuna tuning (moderate depth).	0.8744	0.889254
24	Soft voting ensemble of 11, 9, 23 models.	0.8622	0.886169
25	Weighted voting ensemble (11:9 = 7:3), both models tuned individually.	0.8739	0.891203

📝 Notes
🧪 Submission 21 showed that deeper Optuna tuning (with higher CV folds) improves local stability and generalization.

❌ Submission 22 had high local score but poor Kaggle AUC, indicating overfitting to CV folds.

✅ Submission 23 performed well and proved that simplified + clean feature set still generalizes decently.

🔁 Submission 24 ensemble (11+9+23) showed no benefit over base models, possibly due to similar model biases.

🧪 Submission 25 applied weighted voting to tuned 11 and 9, achieving a strong generalization balance.

🚩 Insights & Next Steps
🧠 Over-complexity harms generalization (as seen in 22), while clean models with solid tuning perform better.

🧪 Voting helps only when component models are diverse in error patterns; similar LGBM-based models limit ensemble gain.

🔜 Submission 26 Goal: Try RandomSearch-based tuning of 11 and 9, then soft voting ensemble → further validate if tuning route affects model synergy.