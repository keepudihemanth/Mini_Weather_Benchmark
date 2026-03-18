# 🌦️ Mini WeatherBench: Temperature Forecast Benchmark using ERA5

##  Overview

This project implements a **WeatherBench-inspired benchmarking framework** for temperature forecasting using ERA5 reanalysis data. It evaluates multiple **machine learning and deep learning models** for deterministic weather prediction at a regional scale.

The goal is to compare models based on their ability to predict **24-hour ahead temperature** and analyze how **dataset size affects model performance and generalization**.

---

##  Objectives

* Build a **temperature forecasting pipeline** using ERA5 data
* Compare multiple **ML models vs baseline**
* Evaluate performance using **MAE and RMSE**
* Analyze **generalization on unseen data (Jan 2026)**
* Study the **impact of dataset size (1 month vs 6 months)**
* Extend benchmarking with **Deep Learning models (LSTM/GRU)**

---

##  Dataset

* Source: Copernicus Climate Data Store (ERA5)
* Variable: **2m Temperature (t2m)**
* Format: NetCDF (.nc)
* Resolution: Hourly

### Datasets Used

| Dataset           | Description                |
| ----------------- | -------------------------- |
| 1 Month           | Initial training dataset   |
| 6 Months          | Extended training dataset  |
| Jan 2026 (1 week) | Out-of-sample test dataset |

---

##  Data Preprocessing

* Convert temperature from **Kelvin → Celsius**
* Convert NetCDF → Pandas DataFrame
* Create **lag features (past 24 hours)**
* Create **forecast targets (t+24 hours)**
* Regional data converted to **mean temperature time series**

---

##  Models Implemented

### Baseline

* Persistence Model (t → t+24)

###  Machine Learning Models

* Linear Regression
* Random Forest
* Gradient Boosting
* XGBoost
* Support Vector Regression (SVR)

###  Deep Learning Models (Planned/Extended)

* LSTM
* GRU

---

##  Evaluation Metrics

* **MAE (Mean Absolute Error)**
* **RMSE (Root Mean Squared Error)**

---

##  Results Summary

### 🔸 6-Month Training + Jan 2026 Test

| Model                 | MAE (°C) | RMSE (°C) |
| --------------------- | -------- | --------- |
| **Linear Regression** | **0.31** | **0.37**  |
| Gradient Boosting     | 0.79     | 1.07      |
| Random Forest         | 0.87     | 1.15      |
| XGBoost               | 0.98     | 1.31      |
| SVR                   | 1.53     | 2.05      |

---

##  Key Findings

* Increasing dataset size (**1 month → 6 months**) reduced error significantly
* **Linear Regression consistently outperformed complex models**
* Tree-based models initially overfit but improved with more data
* Simple models generalize better for **short-term temperature forecasting**
* Temperature time series exhibits **strong linear and periodic patterns**

---

##  Experiments Conducted

1. Benchmark using 1-month dataset
2. Generalization test on Jan 2026
3. Benchmark using 6-month dataset
4. Final generalization test (Jan 2026)
5. (Extension) Deep learning comparison

---

##  Future Work

* Add **multi-horizon forecasting (24h, 48h, 72h)**
* Include **additional weather variables** (pressure, wind)
* Implement **spatial grid forecasting**
* Compare with **deep learning models (LSTM/GRU)**
* Extend to **longer time spans (1 year+)**

---

##  Tech Stack

* Python
* NumPy, Pandas
* Scikit-learn
* XGBoost
* Xarray (NetCDF processing)
* Matplotlib
* PyTorch / TensorFlow (for DL models)

---

##  Conclusion

This project demonstrates a **simplified WeatherBench-style benchmarking approach** for temperature forecasting. It highlights the importance of dataset size, model complexity, and generalization in time-series prediction tasks.

---

## Acknowledgements

* ERA5 dataset from Copernicus Climate Data Store https://cds.climate.copernicus.eu/datasets
* Inspired by WeatherBench (Google Research)

---

##  Contact

Feel free to reach out for collaboration or suggestions!
