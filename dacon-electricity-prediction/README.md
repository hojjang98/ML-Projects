# DACON Electricity Usage Prediction AI Competition

This repository contains my solution for the **DACON Electricity Usage Prediction AI Competition**.  
The goal of the competition is to predict the hourly **electricity consumption (kWh)** for each building using weather and building-specific features.

<br>

## 📁 Project Structure

```bash

├── data/                     # Raw data (train.csv, test.csv, building_info.csv, etc.)
├── notebooks/                # EDA and experiment notebooks
├── models/                   # Saved models and weights
├── outputs/                  # Prediction results and submission files
├── utils/                    # Preprocessing and helper functions
└── main.py                   # Main pipeline script

```

## 🔍 Problem Overview

- **Objective**: Predict hourly electricity usage for buildings  
- **Target Variable**: `전력소비량(kWh)` (Electricity Consumption)  
- **Features**:
  - **Weather**: temperature, rainfall, wind speed, humidity, sunshine duration, solar radiation  
  - **Building**: building type, total area, cooling area, solar panel capacity, ESS storage, PCS capacity  

⚠️ **Note**: Since the competition was hosted in Korea, all dataset columns are in **Korean**  
(e.g., `건물유형` = building type, `전력소비량` = electricity consumption, `냉방면적` = cooling area).  
All preprocessing and modeling steps were performed while handling these Korean-language variables.

The task is formulated as a **regression problem**, where the model is trained on historical hourly electricity usage and corresponding features.

<br>

## 🛠 Technologies Used

- Python (pandas, numpy, scikit-learn)  
- LightGBM, XGBoost  
- Optuna (Hyperparameter Tuning)  
- Visualization: matplotlib, seaborn  
- Environment: Jupyter Notebook, Google Colab  

<br>

## ✅ Future Improvements

- Add time-series features (e.g., lag, rolling averages)  
- Explore AutoML frameworks (PyCaret, H2O, AutoGluon)  
- Improve ensembling techniques (e.g., stacking, weighted blending)  
- Consider weather forecast data as external input  

<br>

## 📌 References

- [Competition Page (DACON)](https://dacon.io/competitions/official/236531/overview)  
- Submission format: refer to `sample_submission.csv`  

<br>

## 📤 Model Release Plan

All final models, weights, and training pipelines will be uploaded **after the competition officially ends**, in accordance with DACON's rules.  
Until then, only logs, code structure, and local experimentation details will be maintained in this repository.

## 📂 Dataset Overview

The dataset is composed of three main files:

1. **train.csv**  
   - Hourly electricity consumption data for each building  
   - **Key columns**:  
     - `num_date_time`: Datetime index  
     - `건물번호`: Building ID (foreign key linked to `building_info.csv`)  
     - `전력소비량(kWh)`: Electricity consumption (target variable)

2. **test.csv**  
   - Same structure as `train.csv` **without the target column**  
   - Used for generating competition submissions

3. **building_info.csv**  
   - Metadata for each building  
   - **Key columns**:  
     - `건물번호`: Building ID  
     - `건물유형`: Building type (categorical)  
     - `연면적`: Total floor area (㎡)  
     - `냉방면적`: Cooling area (㎡)  
     - `태양광용량`: Solar panel capacity (kW)  
     - `ESS저장용량`: ESS storage capacity (kWh)  
     - `PCS용량`: PCS capacity (kW)

---

### Target Variable

- **`전력소비량(kWh)`**: Hourly electricity usage for each building  

---

### Features Summary

| Category      | Feature Examples                                      |
|---------------|-------------------------------------------------------|
| **Temporal**  | `num_date_time` (datetime, can be expanded into hour, weekday, month, season, holiday flags) |
| **Building**  | `건물유형`, `연면적`, `냉방면적`, `태양광용량`, `ESS저장용량`, `PCS용량` |
| **Target**    | `전력소비량(kWh)` (only in `train.csv`)                |

⚠️ Feature names are in **Korean**, requiring preprocessing steps to handle column names and categorical encoding.

