# Chocolate Chip Cookie Pricing & Forecasting Model

## Project Overview
This predictive analytics project was developed as part of the **Boston University MBA program** to evaluate the effectiveness of time-trend data and seasonal variables in forecasting consumer product pricing. 

The objective is to determine if a baseline macroeconomic trend combined with quarterly seasonality can serve as an effective, lean predictor for future chocolate chip cookie prices, without relying on granular, volatile commodity ingredient costs (e.g., flour, sugar, cocoa).

## Dataset & Source
* **Data Source:** Federal Reserve Economic Data (FRED)
* **Granularity:** Historical daily/periodic price tracking and date sequencing.
* **Target Variable:** Continuous price of chocolate chip cookies.

## Feature Engineering & Methodology
To isolate structural trajectory from short-term market noise, the following features were engineered directly from the raw time-series data using Python (`pandas`):
* **Time Trend:** A deterministic sequential counter tracking long-term macroeconomic momentum.
* **Seasonality Dummies ($Q1$, $Q2$, $Q3$):** Categorical dummy variables to isolate structural shifts in quarterly demand.
* **Lagged Price ($t-1$):** Used to capture autoregressive price stickiness from the immediate prior period.

An **Ordinary Least Squares (OLS) Regression** was fitted using the `statsmodels` architecture to analyze the statistical significance ($p$-values) of each predictor and establish an overall model fit ($R^2$).

## Risk Management & Prediction Bands
To make the model operationally viable for business budgeting, a custom forecasting engine was constructed utilizing the model's **Residual Standard Error**. 
* **Target Forecast:** Evaluated at a future milestone (Trend = 300, $Q3$ active, Lagged Price = \$1.15).
* **Confidence Boundaries:** Modeled using standard managerial parameters of $\pm 2$ Standard Errors to establish a robust **95% Upper and Lower Risk Band** for operational price protection.

## Technical Stack
* **Language:** Python
* **Environment:** JupyterLab
* **Core Libraries:** `pandas`, `statsmodels` (OLS regression engine), `matplotlib` & `numpy` (visualization architecture).
