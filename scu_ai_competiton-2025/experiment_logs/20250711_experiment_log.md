## 🗕️ Experiment Log 🟩 Day 17 (Final Submissions: 81–85)

> 🏁 **This marks the final day of experimentation for this competition.**

### 🧪 Summary Table

| Submission | Description                                                        | Local AUC | Kaggle AUC |
|------------|--------------------------------------------------------------------|-----------|------------|
| 81         | Voting (6:2:2), only **Behavior + Purchase Clustering** retained   | 0.8790    | 0.896511 🔼 |
| 82         | **Soft Blending of predictions** from 4 top submissions (`5`, `11`, `61`, `73`) | –         | 0.901946 ⬆️ |
| 83         | **Soft Blending** using only top 3 files (`11`, `61`, `73`)        | –         | **0.902074** 🏆 **Best** |
| 84         | Soft Blending using 4 files (`5`, `11`, `61`, `73`)                | –         | 0.901613 🔽 |
| 85         | Soft Blending between submission `82`, `83`, and `84`              | –         | 0.901986 ⬆️ |

---

### 📝 Notes

- ✅ **Submission 81** simplified clustering by keeping only **Behavior and Purchase clusters**. The result was **stable** and maintained high leaderboard AUC.
- 🤖 **Submissions 82–85** explored **file-based ensemble blending** (soft averaging of predictions).
- 📈 **Submission 83** (top 3 files only) achieved the **highest leaderboard score** to date: **0.902074**.
- 🔁 Adding more models to the blend (as in 84) did **not always help**, suggesting a sweet spot exists.
- 📊 Final blend (85) combining previous blends (82–84) was **strong but not superior** to the simpler 83.

---

### 🚩 Final Takeaways

- ✅ **Soft blending** of well-performing predictions is a powerful late-stage technique.
- ✅ Limiting the blend to **top 3 predictions** yields optimal generalization.
- 🚫 Excessive blending (adding `5.submission`) slightly hurt performance.
- 🧠 Overall, **ensemble diversity + prediction synergy** beats complexity.

---

### 🔚 The End

🏆 With **83.submission** scoring **0.902074**, this concludes all model experimentation.  
📦 All critical models, features, and ensemble strategies have been thoroughly explored.
💡 Time to **document findings**, **share insights**, and move forward with confidence!

