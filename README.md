# E-Commerce Demand Forecasting (LightGBM)

A multi-category time series forecasting model to predict weekly sales demand and optimize inventory levels.

## Overview
Inaccurate demand forecasts lead to either excess holding costs (overstock) or lost sales (stockouts). This project builds a forecasting model on Brazilian e-commerce transaction data (Olist) to predict weekly units demanded across top product categories.

## Methodology
- **Dataset:** Olist E-Commerce dataset (orders, items, products).
- **Time Aggregation:** Resampled transactions to weekly totals for the top 5 product categories.
- **Feature Engineering:**
  - Lag features ($t-1$, $t-2$, $t-4$ weeks)
  - Rolling averages (4 and 8 weeks)
  - Calendar features (week of year, month)
- **Model:** A single **LightGBM Regressor** trained on historical data (2017 to mid-2018) and evaluated on a strict 10-week out-of-time test set.

## Performance
- **WAPE (Weighted Absolute Percentage Error):** `~19%`
- **Application:** Model forecasts can be directly combined with supplier lead times to calculate dynamic Safety Stock and Reorder Points (ROP).

## Visual Output
![Demand Forecast](demand_forecast_chart.png)

## How to Run the Project
The full code is available in the interactive notebook. You can run it with a single click:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Oi7rcxyWxkUe-86vEbmTnPwmb2kiftkm)
