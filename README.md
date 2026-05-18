# 💊 PharmaCast

### Predicting Demand. Protecting Patients. Optimising Inventory.
![Python](https://img.shields.io/badge/Python-3.11-blue)
![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-orange)
![pandas](https://img.shields.io/badge/pandas-data_analysis-brown)
![matplotlib](https://img.shields.io/badge/matplotlib-visualize-yellow)
![Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-green)
---

![pharm](pharm_cast.png)

## 🎯 The Problem
One of the most common challenges in the pharmaceutical supply chain is **inventory distortion** — the imbalance between overstocking and understocking. 

**For a typical retail business, a stockout means a lost sale. In the pharmaceutical industry, the stakes are infinitely higher — it can mean a delay in life-saving treatment. This immense responsibility is why effective pharmacy inventory forecasting is not just a good business practice, but a critical component of patient safety.**


---

## The Solution

PharmaCast predicts medication demand to help pharmacies:
- reduce stockouts
- avoid overstocking
- improve procurement decisions

---


## Architecture

```
Raw Sales Data
      ↓
EDA & Decomposition
      ↓
Feature Engineering
      ↓
Model Training
      ↓
 Evaluation
      ↓
Inventory Insights
```
---

## 💡 Key Insights

-  Paracetamol drives 49.4% of total sales  
-  Annual seasonality is strong  
-  Weekly seasonality is negligible  
-  Saturday is the busiest day  
-  Linear Regression performed nearly as well as Random Forest
---

## 📁 Project Structure

```
PharmaCast/
│
├── data/
│   └── pharma-sales-data/         # Place dataset here (not tracked by git)
│       └── salesdaily.csv
│
├── outputs/                       # Generated plots saved by the notebook
│   ├── 01_exploratory_overview.png
│   ├── 01b_drug_composition.png
│   ├── 02_decomposition_comparison.png
│   ├── 03_actual_vs_predicted.png
│   ├── 04_feature_importance.png
│   ├── 05_residual_analysis.png
│   ├── 06_prediction_confidence.png
│   └── 07_scorecard.png
│
├── pharma_sales_forecast.ipynb    # Full narrative analysis notebook
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 📊 The Dataset


The model was trained on a pharmacy sales dataset obtained from Kaggle, containing historical transactional sales records from 2014–2019. 


### Getting the Data

The dataset is not included in this repository. To set it up locally:

**Option 1 — Download manually (recommended)**

1. Go to [https://www.kaggle.com/datasets/milanzdravkovic/pharma-sales-data](https://www.kaggle.com/datasets/milanzdravkovic/pharma-sales-data)
2. Click **Download**
3. Extract and place `salesdaily.csv` at:

```
PharmaCast/data/pharma-sales-data/salesdaily.csv
```

The notebook reads the file from this path. No other configuration is needed.

**Option 2 — Download via kagglehub**

```bash
pip install kagglehub
```

```python
import kagglehub
from kagglehub import KaggleDatasetAdapter

df = kagglehub.load_dataset(
    KaggleDatasetAdapter.PANDAS,
    "milanzdravkovic/pharma-sales-data",
    ""
)
```

> A Kaggle account and configured API token are required for Option 2.  
> See [Kaggle API setup](https://github.com/Kaggle/kagglehub) for instructions.


---


## 🛠️ Getting Started

**1. Clone the repository**
```bash
git clone https://github.com/anaboset/FUTURE_ML_01
cd FUTURE_ML_01
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Add the dataset**

Download `salesdaily.csv` from Kaggle and place it at `data/pharma-sales-data/salesdaily.csv`.  
See [Getting the Data](#getting-the-data) above for full instructions.

**4. Create the outputs folder**
```bash
mkdir outputs
```

**5. Run the notebook**
```bash
jupyter notebook pharma_sales_forecast.ipynb
```

Run all cells from top to bottom. Each chapter builds on the previous one.

---

## ⚠️ Limitations 

- Cannot predict external outbreaks/events
- Requires historical sales data
- Large unexplained spikes still affect accuracy
- Retraining needed monthly

---

## 🚀 Roadmap

- [ ] Dedicated N02BE forecast model — isolating the dominant category's 115% seasonal signal
- [ ] SKU-level forecasting across all 8 drug categories
- [ ] External signals: flu season index, weather, hospital admission rates
- [ ] Event calendar feature: promotions, public holidays, stockout flags
- [ ] Automated monthly retraining pipeline with drift detection
- [ ] Interactive dashboard for non-technical pharmacy staff

---

## 👤 Author's Note

If the forecast helps a single pharmacy avoid a stockout on a critical medication, the project has achieved its purpose.

---

*Built as part of a ML internship portfolio project.
