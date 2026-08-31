# 📦 Demand Forecasting & Ottimizzazione Scorte con LightGBM

## 📌 Executive Summary
La gestione inefficiente delle scorte genera costi elevati di magazzino (*overstocking*) e perdite di fatturato per rottura di stock (*stockout*). Questo progetto modella la domanda settimanale cross-categoria su dati reali di e-commerce per ottimizzare i piani di riordino.

## 🛠️ Architettura Tecnica
- **Dataset:** Olist Brazilian E-Commerce (100k+ ordini).
- **Modello:** LightGBM Regressor (Multi-Series Time Series Forecasting).
- **Feature Engineering:** Lags temporali (t-1, t-2, t-4), Rolling Averages (4 e 8 settimane) e variabili di calendario/stagionalità.
- **Validazione:** Time-based train/test split (ultime 12 settimane come holdout).

## 📊 Metriche & Performance
- **WAPE (Weighted Absolute Percentage Error):** Valutazione ponderata sui volumi reali.
- **Inventory Cost Model:** Quantificazione economica del trade-off tra costi di holding e margine perso per stockout.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Oi7rcxyWxkUe-86vEbmTnPwmb2kiftkm)
