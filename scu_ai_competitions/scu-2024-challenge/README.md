# 🧬 Thyroid Disease Prediction – SCU AI Challenge 2024

This project was completed as part of the **1st AI Modeling Competition** hosted by **Seoul Cyber University** in 2024.  
The objective was to predict whether a patient shows signs of **thyroid dysfunction** using survey responses, medication history, and hormone test results.

> 📌 **Competition Link**: [SCU AI Competition 2024](https://www.kaggle.com/competitions/scu-ai-competition-202401)

---

## 🎯 Objective

Develop a binary classification model to predict the presence of thyroid disease.

- **Type**: Binary Classification  
- **Target Variable**: `target`  
  - `1`: Thyroid disease  
  - `0`: No thyroid disease

---

## 📂 Dataset

The dataset combines categorical and numerical health features.

| Feature Name              | Description                                  |
|---------------------------|----------------------------------------------|
| `나이`                     | Age                                          |
| `성별`                     | Gender                                       |
| `티록신_복용_여부`          | Whether the patient takes thyroxine           |
| `갑상선저하_인지_여부`       | Whether the patient recognizes hypothyroidism |
| `TSH`, `FreeT3`, `FreeT4` | Hormone levels from blood tests               |
| `target`                  | Label (binary outcome)                       |

⚠️ Several columns (e.g., `TSH`, `FreeT3`) contained missing values and required imputation.

---

## ⚙️ Approach

### 🔹 Preprocessing
- Filled missing values with mean or constant values  
- Encoded categorical variables (`OneHotEncoder`)  
- Scaled continuous variables (`MinMaxScaler`)

### 🔹 Feature Engineering
- Aggregated binary health indicators (e.g., total “yes” counts)  
- Created interaction features from combinations of status variables  
- Added hormone-level ratio features (e.g., `FreeT4 / FreeT3`)

### 🔹 Modeling
- Baseline: `RandomForestClassifier`  
- Final: `LightGBMClassifier` with cross-validation  
- Feature selection using **SelectPercentile**

---

## 🧪 Results

- **Final Model**: LightGBMClassifier  
- **Validation Metric**: F1 (macro)  
- **Outcome**: Improved performance after feature selection and class balance handling  

---

## 📁 Repository Layout

```bash

scu-2024-challenge/
├── data/                 # Train/test data (not uploaded)
├── notebooks/
│   └── scu_competition.ipynb
├── README.md

```

## 📓 Refactored Notebook (Cleaned and Commented)

The final notebook was restructured to improve readability and reproducibility.  
Key improvements include:

- **Modular workflow**: Clear separation of preprocessing, feature engineering, model training, and evaluation  
- **Concise comments**: Explanations focus on purpose rather than step numbering  
- **Reduced redundancy**: Simplified loops and functions for data handling  
- **Visualization support**: Added plots to show feature selection performance and validation results  

👉 Access the notebook here:  
[scu_2024_ai_competiton.ipynb](https://github.com/hojjang98/scu_ai_competitions/blob/main/scu-2024-challenge/notebooks/scu_2024_ai_competiton.ipynb)

---

## 🧠 Key Learnings

- **Health indicators** such as pregnancy status and chronic disease history provided strong predictive power  
- **Hormone-level features** (e.g., TSH, FreeT3, FreeT4) required careful preprocessing due to missing values and skewed distributions  
- **LightGBM** handled the mixed data types (categorical + numerical) effectively  
- **Simplicity in features** often outperformed overly complex transformations, emphasizing the importance of interpretability
