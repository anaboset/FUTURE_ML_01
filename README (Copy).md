# 💊 PharmCast
### Predicting Demand. Protecting Patients. Optimising Inventory.

---
![forecast_pharm](forecast_pharm.png)
One of the most common challenges in the pharmaceutical supply chain is **inventory distortion** — the imbalance between overstocking and understocking. 

For a typical retail business, a stockout means a lost sale. In the pharmaceutical industry, the stakes are infinitely higher — it can mean a delay in life-saving treatment. This immense responsibility is why effective pharmacy inventory forecasting is not just a good business practice, but a critical component of patient safety.

This project builds a **machine learning forecasting model** that helps pharmacies anticipate demand and make smarter inventory decisions using historical sales data.

---

## 🎯 The Problem

Pharmacies often struggle to answer:

* How much of each drug category should we stock?
* When will demand spike or drop?
* How can we reduce waste without risking shortages?

---

## 💡 Proposed Solution

This project develops a **time-series forecasting pipeline** that:

* Predicts future demand based on historical patterns
* Captures short-term trends and weekly seasonality
* Provides insights to support inventory planning decisions

---

## 📁 Project Structure

```
pharma-forecast/
│
├── data/
│   └── sales.csv                  # Daily sales records (date, total_sales)
│
├── src/
│   ├── features.py                # Feature engineering pipeline
│   ├── train.py                   # Model training (RF + Linear Regression)
│   ├── evaluate.py                # MAE, RMSE, MAPE, R² metrics
│   ├── decompose.py               # Time-series decomposition
│   └── visualize.py               # Residual analysis & confidence plots
│
├── outputs/                       # Generated plots and saved models
│
├── pharma_sales_forecast.ipynb    # Full narrative analysis notebook
└── README.md
```

---

## 📊 Key Features

| Feature | Description |
|---------|-------------|
| **Time-Series Decomposition** | Separates sales into trend, seasonality, and residual noise |
| **Lag & Rolling Features** | Teaches the model that yesterday's sales predict today's |
| **Dual Model Comparison** | Random Forest vs. Linear Regression to validate complexity |
| **Residual Analysis** | Diagnoses *where* and *when* the model struggles |
| **Confidence Scoring** | Classifies every forecast as High / Medium / Low confidence |
| **Business Recommendations** | Translates model output into procurement and staffing actions |

---

## 📈 Results 

| Metric | Linear Regression | Random Forest |
|--------|:-----------------:|:-------------:|
| MAPE   | —                 | —             |
| RMSE   | —                 | —             |
| R²     | —                 | —             |

> *Fill in after running the notebook on your data.*  
> A MAPE below 10% indicates forecasts are operationally reliable for inventory planning.

---

## 🛠️ Getting Started

**1. Install dependencies**
```bash
pip install -r requirements.txt
```

**2. Add your data**  
Place a CSV file at `data/sales.csv` with at minimum these two columns:
```
date, total_sales
2023-01-01, 4820
2023-01-02, 3915
...
```

**3. Run the notebook**
```bash
jupyter notebook pharma_sales_forecast.ipynb
```

---

## ⚠️ Limitations 


- Model does not account for external factors (weather, outbreaks)
- Assumes historical patterns remain stable
- Aggregated demand hides product-level variation

---

## 🚀 Future  Improvements

- [ ] SKU-level forecasting (product-by-product, not just total sales)
- [ ] External signals: weather, local events, flu season index
- [ ] Event calendar integration (promotions, holidays, stockout flags)
- [ ] Automated retraining pipeline with drift detection
- [ ] Dashboard for non-technical pharmacy staff

---

## 👤 Author's Note

If the forecast helps a single pharmacy avoid a stockout on a critical medication, the project has achieved its purpose.

---

*Built with Python · scikit-learn · statsmodels · pandas · matplotlib*
