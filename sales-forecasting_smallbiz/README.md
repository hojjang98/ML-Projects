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
- There are clear **seasonal trends** in sales volume, especially for food-related sectors.
- **Some industries are highly location-sensitive**, while others perform evenly across districts.

---

## 📂 Files

- `sales_EDA.ipynb`:  
  Cleaned notebook with grouped bar charts, boxplots, and descriptive stats.  
  All visuals and commentary are written in English for clarity.

---

## 🧩 Next Steps

This notebook is Part 1 of a multi-step analysis:
1. **[✓ Done]** Industry- and district-level trend exploration  
2. **[🔜 Upcoming]** Modeling expected sales:  
   "If you open a business in a specific district, how much can you expect to earn?"  
   → Regression-based prediction models using location and industry features

More insights, models, and visualizations will be added as the project evolves 🚀
