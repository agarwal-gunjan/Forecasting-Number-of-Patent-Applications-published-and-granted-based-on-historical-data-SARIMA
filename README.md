# Forecasting-Number-of-Patent-Applications-published-and-granted-based-on-historical-data-SARIMA
This project involves time series forecasting of weekly published and granted Indian patent applications using the SARIMA model. The goal is to analyze historical trends and predict future patent activity, aiding policy-makers, researchers, and innovators.

##  Project Overview

- Developed separate SARIMA models for **published** and **granted** patent applications.
- Weekly data collected from the official government website (data.gov.in) .
- Performed:
  - Outlier removal
  - Stationarity checks (ADF test, differencing)
  - Forecast evaluation (MAE, RMSE)

---

##  Dataset

- **Source:** data.gov.in
- **Frequency:** Weekly
---

##  Tools & Technologies

- Python (Pandas, NumPy, Matplotlib, Statsmodels)
- SARIMA (Seasonal ARIMA)

---

## 📊 Output

- Forecast graphs for up to **52 weeks into the future**

The study also examines the impact of outlier handling on forecasting accuracy for both datasets.
