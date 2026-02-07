# Time Series Analysis of Bitcoin Price (2017–2025)

A comprehensive time series analysis and forecasting study of Bitcoin prices using R, spanning from 2017 to 2025 with hourly-interval data collected from Binance's API.

## 📊 Project Overview

This project conducts an in-depth time series analysis of Bitcoin price movements to explore trends, identify patterns, and develop predictive models using statistical forecasting techniques, specifically ARIMA-based approaches.

### Key Statistics
- **Time Period:** 2017 – 2025 (8 years)
- **Data Frequency:** Hourly intervals
- **Total Observations:** 60,000+ hours
- **Data Source:** Binance API
- **Language:** R

### Data Composition
- **Open, High, Low, Close (OHLC) prices**
- **Trading volume**
- **Price volatility metrics**

## 🎯 Objectives

1. **Explore Bitcoin's price trends and volatility** over an 8-year period
2. **Identify the most suitable statistical forecasting model** for cryptocurrency time series
3. **Evaluate forecasting performance** using error metrics (RMSE, MAE)
4. **Develop insights** into Bitcoin's price behavior and predictive reliability
5. **Provide a foundation** for cryptocurrency market forecasting

## 📈 Methodology

### 1. **Exploratory Data Analysis (EDA)**
- Understand dataset structure, trends, and seasonality
- Identify anomalies and potential data quality issues
- Visualize price movements over time

### 2. **Stationarity Testing**
- Conduct Augmented Dickey-Fuller (ADF) tests
- Apply differencing to achieve stationarity
- Monitor residual autocorrelation

### 3. **ARIMA Model Development**
- Fit AutoRegressive Integrated Moving Average (ARIMA) models
- Perform model selection and hyperparameter tuning
- Analyze ACF and PACF plots for parameter identification

### 4. **Forecasting**
- Generate predictions on test set
- Evaluate model performance using RMSE and MAE
- Visualize predicted vs. actual values

## 📊 Results & Findings

### Model Performance
- **RMSE:** 34,373.64
- **MAE:** 27,061.20

### Key Insights

1. **Trend Capture:** ARIMA successfully captured the general trend of Bitcoin prices, though it struggled with sudden price jumps and regime shifts.

2. **Volatility Challenge:** The high RMSE (≈$34,373) indicates the model's difficulty in fully generalizing to future price behavior, primarily due to Bitcoin's inherent volatility.

3. **Residual Dependencies:** Autocorrelation analysis revealed lingering dependencies in residuals, suggesting:
   - Non-stationary behavior persists despite differencing
   - Cryptocurrency markets exhibit random walk characteristics
   - Complex, non-linear patterns exist beyond ARIMA's scope

4. **Model Limitations:** 
   - ARIMA assumes linear relationships and constant variance
   - Cannot capture sudden market shocks or sentiment-driven price movements
   - Struggles with long-term dependency patterns in cryptocurrency markets

## 🔧 Data Pipeline

### Data Collection (Python)
Due to Binance API rate limits, a Python pipeline was implemented to:
- Make iterative API calls with strategic delays
- Extract 60,000+ hourly observations
- Handle API request limits gracefully
- Store data in structured format for analysis

### Data Analysis (R)
- Load and preprocess Bitcoin price data
- Perform time series decomposition
- Conduct stationarity tests and transformations
- Fit and evaluate ARIMA models
- Generate forecasts and performance metrics

## 🚀 Getting Started

### Prerequisites
```
R >= 4.0
Python 3.7+ (for data collection)
```

### R Libraries Required
```r
install.packages(c(
  "tseries",      # ADF tests
  "forecast",     # ARIMA modeling
  "ggplot2",      # Visualization
  "dplyr",        # Data manipulation
  "tidyr"         # Data tidying
))
```

### Python Libraries (for data collection)
```
pandas
requests
python-binance
numpy
```

### Installation & Setup
```bash
git clone <repository-url>
cd bitcoin-time-series-analysis

# Run data collection (if needed)
python data_collection.py

# Open and run the notebook in R
# In R or RStudio:
# Run: rmarkdown::render("TSAC_Bitcoin_Analysis.Rmd")
```

## 📂 Project Structure

```
.
├── TSAC_Bitcoin_Analysis.ipynb    # Main analysis notebook (R)
├── data_collection.py             # Python pipeline for API data extraction
├── bitcoin_data.csv               # Raw OHLC data (60,000+ rows)
├── requirements.txt               # Python dependencies
├── README.md                       # This file
└── outputs/
    ├── price_trends.png           # Time series visualization
    ├── acf_pacf_plots.png         # Autocorrelation analysis
    ├── forecast_comparison.png    # Predicted vs actual prices
    └── diagnostics.png            # Model diagnostics
```

## 📋 Notebook Contents

### Section 1: Introduction
- Background on cryptocurrency market volatility
- Data collection methodology from Binance API
- Research objectives and scope

### Section 2: Model Specification
- **Exploratory Data Analysis:** Trend, seasonality, and anomaly detection
- **Stationarity Testing:** ADF tests and differencing strategies
- **ACF/PACF Analysis:** Parameter identification for ARIMA(p,d,q)

### Section 3: ARIMA Model Development
- Model fitting and diagnostics
- Residual analysis and autocorrelation checks
- Model selection criteria (AIC, BIC)

### Section 4: Forecasting & Evaluation
- Generate predictions on test set
- Calculate RMSE and MAE performance metrics
- Visualize forecast accuracy

### Section 5: Conclusion & Future Work
- Summary of findings
- Limitations of ARIMA approach
- Recommendations for future research

## 💡 Key Findings & Limitations

### What ARIMA Did Well
✅ Captured long-term trend direction
✅ Provided structured statistical framework
✅ Identified baseline forecasting baseline

### What ARIMA Missed
❌ Sudden price jumps and regime shifts
❌ Time-varying volatility
❌ Non-linear patterns and market sentiment effects
❌ Black swan events and market shocks

## 🔮 Future Work Recommendations

To improve Bitcoin price forecasting, consider:

1. **GARCH Models:** Capture time-varying volatility characteristics
   - GARCH(1,1) for variance modeling
   - EGARCH for asymmetric volatility

2. **Random Walk with Drift:** Model stochastic cryptocurrency trends
   - Better suited for efficient market assumptions
   - Simpler baseline for comparison

3. **Machine Learning Approaches:**
   - LSTMs for capturing long-term temporal dependencies
   - Attention mechanisms for identifying important time periods
   - XGBoost with engineered features for non-linear relationships

4. **Hybrid Models:**
   - Combine ARIMA with machine learning (AutoML)
   - Ensemble methods for improved predictions

5. **External Variables:**
   - Market sentiment from social media (Reddit, Twitter)
   - Trading volume and order book dynamics
   - Macroeconomic indicators
   - Regulatory news and announcements

## 📊 Performance Metrics Interpretation

| Metric | Value | Interpretation |
|--------|-------|-----------------|
| **RMSE** | $34,373.64 | Average prediction error magnitude (penalizes larger errors) |
| **MAE** | $27,061.20 | Average absolute prediction deviation from actual prices |
| **RMSE/MAE Ratio** | 1.27 | Indicates presence of occasional large errors beyond typical deviations |

## 🎓 Learning Outcomes

This project demonstrates:
- Time series decomposition and visualization techniques
- Stationarity testing and data transformation methods
- ARIMA model specification, fitting, and diagnostics
- Forecasting and performance evaluation in finance
- Limitations of statistical models on complex, volatile data
- The importance of model selection based on data characteristics

## 📝 Author

**Khelili Selma**  
Course: TSAC 2024/2025  
Date: March 2025

## 📚 References

- Box, G. E., Jenkins, G. M., Reinsel, G. C., & Ljung, G. M. (2015). Time Series Analysis: Forecasting and Control.
- Nakamoto, S. (2008). Bitcoin: A peer-to-peer electronic cash system.
- Engle, R. F. (1982). Autoregressive conditional heteroscedasticity with estimates of the variance of UK inflation.
- Time series forecasting best practices and methodologies

## 📄 License

This project is submitted as part of the TSAC (Time Series and Advanced Classification) course.

---

**Project Submission Date:** March 2025  
**Analysis Period:** 2017–2025  
**Note:** This analysis is for educational purposes and should not be used as financial advice.
