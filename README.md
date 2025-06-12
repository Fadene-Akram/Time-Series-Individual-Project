# 📊 Time Series Analysis of COVID-19 Cases in Algeria

> 🏫 **National Higher School of Artificial Intelligence**  
> 📅 **Individual Project 2024/2025**  
> 👨‍🎓 **By Student: Akram FADENE**

---

## 📌 Project Title

**Time Series Analysis of Daily New Confirmed COVID-19 Cases per Million People in Algeria**

---

## 🧠 1. Abstract

This study analyzes the daily new confirmed COVID-19 cases per million people in Algeria using a **7-day rolling average** to smooth short-term fluctuations. Given limited testing capacity, the reported case counts likely underestimate actual infections.  

Using data from the **World Health Organization (WHO)** (2025) and **population estimates** (2024), this research examines **historical trends**, **peak infection periods**, and **future forecasts** through time series analysis. The findings provide insights into the **pandemic's trajectory**, helping inform **public health policies** and **preparedness strategies**.

---

## 📖 2. Introduction

Understanding how infectious diseases spread is crucial for public health decisions. COVID-19 disrupted healthcare, economies, and everyday life globally. Monitoring new confirmed daily cases per million people in Algeria provides insights into the virus’s progression and the effectiveness of containment measures.

This dataset, compiled from the WHO (2025) and population estimates (2024), helps us identify trends, fluctuations, and the impact of interventions like lockdowns and vaccines. The use of a **7-day rolling average** improves clarity by reducing noise. However, testing limitations mean reported cases may not fully reflect true infections.

Studying this data allows officials and researchers to evaluate past efforts and prepare for future outbreaks.

---

## 📂 3. Data Processing & Exploration

### 3.1 Load & Explore Dataset  
*(Code-based step: dataset loaded, previewed, and prepared for time series)*

### 3.2 Data Cleaning
- Checked for and handled missing values.
- Converted the date column to datetime format.
- Created a time series object for analysis.

### 3.3 Summary Statistics
- Basic descriptive stats computed to understand distribution and magnitude.

---

## 📈 4. Time Series Visualization

### 🔹 4.1 Original Time Series
- Raw data shows clear spikes around 2021 and 2022.

### 🔹 4.2 Trend Component
- Rising trend until 2021, followed by a decline and stabilization post-2023.

### 🔹 4.3 Seasonal Component
- Cyclic peaks, indicating seasonal effects (e.g., waves or annual trends).

### 🔹 4.4 Residual Component
- Captures irregular variations. Stability improves after 2023.

---

## ⚙️ 5. Stationarity & Differencing

### 5.1 Stationarity Check
- Used ADF/KPSS tests to evaluate stationarity.

### 5.2 First Differencing
- Applied differencing to stabilize mean and make series stationary.

---

## 🔮 6. Forecasting & Evaluation

### 6.1 Candidate Models
- Evaluated ARIMA and SARIMA models.

### 6.2 Best Overall Model: `ARIMA(5,1,1)(1,1,1)[7]`
- **AIC**: -979.9192 → strong balance of fit and simplicity.
- **BIC**: -930.57 → confirms model efficiency.
- **RMSE**: 0.03048 and **MAE**: 0.02825 → strong predictive accuracy.
- **Residual ACF1**: -0.0149 → minimal autocorrelation, desirable for residuals.

---

## 🧪 7. Diagnostic Results

- **Shapiro-Wilk Test**: Residuals not normally distributed (p < 2.2e-16).
- **Box-Pierce Test**: No significant autocorrelation (p = 0.5301).
- **Runs Test**: Residuals show randomness (p = 0.09274).

These indicate the ARIMA model successfully captured the underlying pattern.

---

## ✅ Conclusion

This project successfully analyzed the progression of COVID-19 cases in Algeria using time series techniques. The ARIMA(5,1,1)(1,1,1)[7] model provided accurate forecasts and revealed meaningful trends and seasonality.

While real case counts may be underreported, this analysis still offers valuable support for future pandemic response planning.

---

## ▶️ How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/covid19-algeria-analysis.git
