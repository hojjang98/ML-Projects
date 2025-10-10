# Social Sentiment Monitor – Economic Sentiment vs. Market Reality

This repository contains my personal data science project **Social Sentiment Monitor**,  
which analyzes **economic news sentiment** and compares it with **real-world market indicators (KODEX200, KOSPI)**.  
The goal is to explore whether the emotional tone of media coverage reflects or diverges from actual market trends.

---

## 🔍 Project Overview

- **Objective**: Quantify and analyze emotional tones (positive, neutral, negative) in economic news articles.  
- **Goal**: Compare the aggregated sentiment with financial indices such as **KODEX200** and **KOSPI**.  
- **Approach**:  
  1. Crawl news data from Naver News using economic keywords.  
  2. Apply pre-trained Korean sentiment analysis models (KoBERT / KcELECTRA).  
  3. Collect KODEX200 index data (via `yfinance`).  
  4. Compare sentiment trends with real market performance.

⚠️ **Note:**  
This project is purely analytical and exploratory.  
The sentiment results are **not financial advice**, and the analysis is conducted for educational and research purposes.

---

## 📁 Project Structure

```text
social_sentiment_monitor_economy/
├── data/               # Raw and processed datasets
├── src/                # Crawling and sentiment analysis scripts
├── results/            # Visualizations and correlation outputs
├── README.md           # Public documentation
└── project_plan.docx   # Internal planning notes (not uploaded to GitHub)

## 📊 Data Description

| Type | Source | Description |
|------|---------|-------------|
| **News Articles** | Naver News | Keywords: economy, inflation, housing, interest rate, etc. |
| **Sentiment Model** | Hugging Face | KoBERT / KcELECTRA pre-trained models |
| **Market Index** | Yahoo Finance (`yfinance`) | KODEX200 daily close & percent change |

Each article is analyzed for sentiment polarity, aggregated by date and media outlet,  
and compared to the same-day KODEX200 performance.

---

## 🧭 Analysis Roadmap

| Week | Focus | Deliverable |
|------|--------|-------------|
| **Week 1** | Collect economic news data | `data/economic_news.csv` |
| **Week 2** | Apply sentiment analysis | `data/sentiment_labeled.csv` |
| **Week 3** | Gather market index data | `data/kodex_1m.csv` |
| **Week 4** | Correlation analysis & visualization | `results/correlation_plot.png` |

---

## 🧠 Hypotheses

- **H1.** Negative media sentiment correlates with market downturns.  
- **H2.** Some media outlets consistently show a negative tone toward economic issues.  
- **H3.** Major economic events (e.g., interest rate decisions) cause noticeable sentiment shifts.

---

## 🛠 Technologies Used

- **Python**: pandas, numpy, requests, BeautifulSoup4  
- **Transformers**: KoBERT, KcELECTRA  
- **Data Source**: Naver News, Yahoo Finance  
- **Visualization**: matplotlib, seaborn  
- **Environment**: Jupyter Notebook, Google Colab  

---

## 📈 Expected Results

- Line chart showing **daily sentiment trend** vs **KODEX200 index movement**  
- Heatmap comparing **media-wise sentiment polarity**  
- Correlation coefficient between **average sentiment** and **market return**

Example interpretation:  
> “As negative sentiment increased during mid-September, KODEX200 experienced a concurrent decline.”

---

## 📌 Future Improvements

- Expand analysis to multiple topics (e.g., environment, welfare, housing).  
- Incorporate **comment-level or SNS-based sentiment** for public perception comparison.  
- Apply **topic modeling (LDA, BERTopic)** to distinguish between inflation, housing, and finance-related subthemes.  
- Explore **Granger causality** between sentiment and market movement.

---

## 📂 References

- [KoBERT Sentiment Model (SKTBrain)](https://github.com/SKTBrain/KoBERT)  
- [KcELECTRA Korean Sentiment Model](https://github.com/Beomi/KcELECTRA)  
- [Yahoo Finance Python API (yfinance)](https://pypi.org/project/yfinance/)  
- [Naver News Search Portal](https://news.naver.com/main/main.naver)

---

## 🧾 License

This project is for educational and non-commercial purposes only.  
All data is collected from **publicly available sources**, respecting fair use.

---

## ✍️ Author

**Hojun Choi (hojjang98)**  
Seoul Cyber University — Big Data & AI Major  
📍 Korea | 🌐 [GitHub](https://github.com/hojjang98)
