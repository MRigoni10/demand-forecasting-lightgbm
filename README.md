# 📦 Demand Forecasting & Scorte E-Commerce con LightGBM

## 📌 Business Problem
L'errata stima della domanda causa perdite economiche su due fronti:
- **Overstocking:** Incremento dei costi di mantenimento a magazzino e immobilizzazione di capitale.
- **Stockout:** Vendite mancate e riduzione della customer satisfaction.

Questo progetto modella la domanda settimanale cross-categoria sull'e-commerce brasiliano Olist per ottimizzare la pianificazione delle scorte.

## 🛠️ Architettura Tecnica
- **Dataset:** 100k+ ordini reali da *Olist E-Commerce*.
- **Modello:** LightGBM Regressor multi-serie su serie storiche aggregate a livello settimanale.
- **Feature Engineering:**
  - Lags di domanda ($t-1, t-2, t-4$)
  - Medie mobili (*Rolling Averages* a 4 e 8 settimane)
  - Variabili di stagionalità e calendario (*Week of Year*, *Month*)
- **Validazione:** Split cronologico (Train: 2017-02 fino a 2018-05, Test: ultime 10 settimane).

## 📊 Risultati & Performance
- **WAPE (Weighted Absolute Percentage Error):** ~18-22% (standard di riferimento per demand forecasting nel retail).
- **MAE:** Misurato in unità vendute a settimana per categoria.

### Visualizzazione: Domanda Reale vs Forecast (Test Period)
![Demand Forecast](demand_forecast_chart.png)

## 💡 Raccomandazioni di Business
1. **Safety Stock Dinamico:** Utilizzare l'errore medio di previsione (RMSE) per calcolare la scorta di sicurezza ottimale in base al livello di servizio desiderato ($95\%$).
2. **Riordino Automatico:** Attivare ordini automatici al fornitore quando lo stock scende al di sotto del *Reorder Point (ROP = Lead Time Demand + Safety Stock)*.
