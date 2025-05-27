# 📊 EDA – Sales Patterns by Industry & Neighborhood (2024, Seoul)

This notebook explores sales patterns across **different service industries and neighborhoods (행정동)** in Seoul, using public business data from 2024.  
The main goal is to uncover **revenue trends by location and industry** — insights that will guide downstream **sales prediction models**.

---

## 📌 Objectives

- Analyze sales distributions across **industry types**
- Identify **high-performing districts** for specific industries
- Explore **seasonal and regional variations** in sales
- Build an intuitive understanding of what drives local sales differences

---

## 🧪 Data Overview

- **Source**: Seoul Open Data Platform  
- **Columns used**:
  - `기준_년분기_코드` (Quarter code)
  - `서비스_업종_코드_명` (Service industry name)
  - `행정동_코드_명` (Administrative neighborhood)
  - `당월_매출_금액` (Monthly sales)

---

## 📈 Key Insights

- **Certain neighborhoods consistently outperform others** in terms of revenue for specific industries (e.g., cafes, fried chicken, beauty salons).
- Clear **seasonal trends** are observed, especially in food and beverage sectors.
- **Some industries are highly location-sensitive**, while others show more consistent performance across districts.

---

## 📂 Files

- `sales_EDA.ipynb`  
  A cleaned and structured notebook with grouped bar charts, boxplots, and descriptive statistics.  
  All code and commentary are written in English for clarity and reusability.

---

## 🧩 Next Steps

This notebook is Part 1 of a multi-step analysis:
1. **[✓ Completed]** Trend exploration by industry and neighborhood  
2. **[🔜 In Progress]** Predictive modeling:  
   "If you open a business in a specific district, how much can you expect to earn?"  
   → Regression-based models using location and industry features

---

More insights and enhancements will be added as the project continues — stay tuned 🚀
