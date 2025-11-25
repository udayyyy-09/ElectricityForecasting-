# 📊 Forecasting and Visualization of Daily Electricity Consumption Using Time Series Analysis

### 📌 Introduction

Electricity consumption fluctuates significantly due to seasonal changes, unpredictable spikes, and day-to-day variations.

This project uses time series analysis to uncover usage patterns, detect anomalies, and lay the foundation for accurate forecasting models.

### 🧭 Project Objectives

1. Analyze daily electricity consumption to identify patterns and structure.

2. Perform time series analysis to detect trend, seasonality, and anomalies.

3. Visualize key insights using clear, data-driven plots and charts.

4. Build a base for forecasting models to improve demand prediction accuracy.

### 🗂️ Dataset Details

Size: 504 rows, 34 columns

Source: Kaggle — State-wise Power Consumption in India

(Search “state-wise power consumption India” on Kaggle)

## 📊 Exploratory Data Analysis (EDA)

Before model building, a detailed Exploratory Data Analysis (EDA) was performed to understand electricity consumption patterns across the Northern region. The analysis included:

- **Total Consumption Over Time**:
  A time-series line plot was used to visualize how overall electricity usage changed daily. This helped identify trends, peaks, and fluctuations in the region.

- **State-wise Latest Consumption**:
  A bar chart of the most recent data highlighted which states consume the highest electricity on the latest available day.

- **Monthly Average Consumption**:
Monthly resampling showed long-term patterns and seasonal behavior for each state, helping understand recurring usage cycles.

- **Consumption Distribution**:
Boxplots displayed the distribution, spread, and outliers for every state's electricity usage.

Additionally, summary statistics and total consumption by state were calculated to understand:

- Mean, min, max, and deviation

- Which states consume the most electricity overall

This EDA provided a clear understanding of the dataset and guided feature selection and model choice.

## 🧹 Data Preprocessing

Before building forecasting models, the dataset was preprocessed to ensure it met the requirements of time series algorithms. The key preprocessing steps included:

1. Handling Stationarity (ADF Test):
The Augmented Dickey-Fuller (ADF) test was applied to check whether the time series was stationary. 

2. Differencing Non-Stationary Series:
If the ADF test showed a non-stationary series (p-value > 0.05), first-order differencing was applied. This helped remove trends and stabilize the mean over time.

3. Visual Comparison:
The original series and its differenced version were plotted to observe improvements in stability and variance.

4. Cleaned Input for Modeling:
After making the series stationary, the processed data was used as input to ARIMA, SARIMA, Prophet, and LSTM models to ensure consistent and reliable forecasting results.


## 📌 Models Implemented

In this project, I implemented four different time series forecasting models — ARIMA, SARIMA, Prophet, and LSTM — and compared their performance on daily electricity consumption data.

1️⃣ ARIMA

ARIMA was used to model non-seasonal patterns in the data. It captured the trend fairly well but struggled whenever seasonality or sudden usage spikes appeared.

2️⃣ SARIMA

SARIMA improved upon ARIMA by handling seasonality. It performed better on data with repeating monthly or weekly patterns but still showed limitations when anomalies occurred.

3️⃣ Prophet

Prophet automatically learned trend + seasonality and worked well even with missing values. It generated smooth forecasts with confidence intervals but tended to oversmooth on smaller datasets.

4️⃣ LSTM

LSTM delivered the best accuracy among all four models.
It successfully learned complex, nonlinear patterns and long-term dependencies in electricity usage. LSTM handled anomalies better than statistical models and produced the most reliable forecasts.

### 📊 Final Comparison

Out of all four models:

- LSTM performed the best

- SARIMA and Prophet gave moderate performance

- ARIMA was the weakest on seasonal or fluctuating data

Below is the screenshot of comparison of performance metrices of all 4 models

<img width="1475" height="570" alt="image" src="https://github.com/user-attachments/assets/ce97cdb0-2985-466c-b410-f9e793d8912b" />

## 📌 Conclusion

Based on the comparison of ARIMA, SARIMA, Prophet, and LSTM, the LSTM model delivered the most accurate and stable forecasts. It effectively captured trends, seasonality, and fluctuations, making it the best choice for predicting future electricity consumption. The final LSTM forecast clearly shows upcoming demand patterns, helping improve planning and energy management.
