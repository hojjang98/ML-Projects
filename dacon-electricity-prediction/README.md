# DACON Electricity Usage Prediction AI Competition

This repository contains my solution for the **DACON Electricity Usage Prediction AI Competition**.  
The goal of the competition is to predict the hourly **electricity consumption (kWh)** for each building using weather and building-specific features.

<br>

## 📁 Project Structure

```bash
.
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

