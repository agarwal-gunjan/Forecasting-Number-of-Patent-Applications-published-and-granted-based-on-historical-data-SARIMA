#  Forecasting Indian Patent Publications & Grants using SARIMA

This project focuses on analyzing and forecasting the **weekly number of published and granted patent applications** in India using the **Seasonal ARIMA (SARIMA)** model. The objective is to understand trends, detect patterns, compare forecasts, and provide insights that can inform policy-making, IP strategy, and R&D planning.

---

## Objective

- Forecast the number of **Published** and **Granted** Indian patents weekly using SARIMA.
- Evaluate model performance **before and after** outlier treatment.
- Perform comparative analysis:
  - Forecast trends
  - Publication-to-grant ratios
  - Grant-to-Publish Ratio
  - Weekly trend gaps

---

## Dataset Overview

- **Source**: [data.gov.in](https://data.gov.in)
- **Frequency**: Weekly
---

##  Tools & Technologies

- **Python**
  - `pandas`, `numpy` for data handling
  - `matplotlib` for visualization
  - `statsmodels` for SARIMA modeling
- **Jupyter Notebook**
- **Git & GitHub** for version control

---

## 🧹 Data Preprocessing

- Converted `PUBLICATION_DATE` to datetime format.
- Resampled data to **weekly counts** for both published and granted applications.
- Merged the two datasets for comparative analysis.
- Handled outliers using the **IQR method** and replaced them with median values.
- Checked for **stationarity** using the **ADF Test**.

---

## 📈 SARIMA Modeling

### ⚙️ Model Configurations

- **Granted Patents**:
  - SARIMA(1, 0, 1)(1, 1, 1, 52)
  - ADF Test: Stationary (d = 0)

- **Published Patents**:
  - SARIMA(2, 1, 1)(1, 1, 1, 52)
  - ADF Test: Non-stationary (d = 1)

### Performance (Before & After Outlier Removal)

| Metric              | Granted (Before) | Granted (After) | Published (Before) | Published (After) |
|---------------------|------------------|------------------|---------------------|---------------------|
| **MAE**             | 784.39           | 140.58           | 368.92              | 347.83              |
| **MSE**             | 909,029.10       | 35,118.02        | 195,254.68          | 161,069.00          |

---

##  Insights & Analysis

###  Final Insights — Granted Forecasting

- The series was stationary and showed annual seasonality.
- SARIMA performed significantly better after cleaning.
- Forecast showed smooth, seasonal fluctuations over 52 weeks.

###  Final Insights — Published Forecasting

- Data was non-stationary; required differencing.
- Slight improvement after outlier removal.
- Forecast showed seasonal but more volatile behavior.

---

##  Comparative Forecasting

- Both series show strong **annual seasonality**.
- Published counts remained consistently higher than granted ones.
- **Granted forecasts were smoother**; published showed occasional spikes.

---

##  Trend Gap Analysis

- Weekly **gap = Published - Granted**
- Gap is mostly positive, indicating **more publications than grants**.
- Occasional spikes hint at policy delays or backlog clearances.

---

##  Ratio Analysis

###  Published-to-Granted Ratio

- **Mean**: ~2.15 → On average, 2.15 patents published for every 1 granted.
- **Min**: 0.0003, **Max**: 43.23 → Huge variation during certain weeks.

###  Granted-to-Published Ratio

- **Mean**: ~0.62 → About 62% of published patents get granted eventually.
- **Range**: 0.35 to 1.06

These ratios help measure **granting efficiency** and **processing lag**.

---

## Overall Conclusion

This project aimed to model, forecast, and compare the weekly trends in Published and Granted patents using SARIMA, along with additional statistical insights. Here's a complete summary of our findings:

- **Published patents consistently outnumber granted patents**, reaffirming backlog concerns in the IP pipeline.
- **Stationarity checks influenced model configurations** (d=0 vs. d=1).
- **Outlier removal greatly improved model accuracy**, especially for granted patents.
- **SARIMA** proved effective in modeling seasonality and trend.
- **Comparative insights** (ratios, trend gaps, forecast spreads) reveal structural delays between publication and grant stages.

This analysis can aid decision-makers, researchers, and innovators in better understanding patent processing trends in India.

---




