# 🍽️ DineIQ Analytics — MenuMatrix Dining Intelligence Platform

> **Data Science Intelligence Arena** | TechWiz Competition  
> Big Data • Apache Spark • Machine Learning • Predictive Restaurant Analytics

---

## 📋 Project Overview

DineIQ Analytics is a full-stack Big Data and Data Science platform that analyzes
large-scale restaurant datasets to deliver:

- **Menu profitability intelligence** (Profit Driver / Volume Driver / Hidden Opportunity / Low Performer)
- **Customer segmentation** (RFM + KMeans clustering)
- **Demand forecasting** (time-series with chronological validation)
- **Wastage intelligence** (ML risk prediction)
- **Market-basket analysis** (Apriori association rules)
- **Promotion effectiveness** (including Promotion Trap detection)
- **Price sensitivity analysis**
- **Multi-location comparison**
- **Sales & rating anomaly detection**
- **Dual analytical pipeline** (Spark MLlib vs Python Scikit-learn comparison)
- **Evidence-based recommendation engine**
- **What-if scenario analysis**

---

## 🛠️ Technology Stack

| Layer | Technology |
|-------|-----------|
| Big Data | Apache Spark 3.x, PySpark, Spark SQL |
| ML (Pipeline A) | Spark MLlib (RF, DT, LogReg) |
| ML (Pipeline B) | Scikit-learn, XGBoost, Ridge Regression |
| Market Basket | MLxtend (Apriori + Association Rules) |
| Backend | Python 3.10+, Pandas, NumPy, SciPy |
| Frontend | Streamlit, Plotly |
| Storage | CSV, Parquet, SQLite |
| Version Control | Git + GitHub |

---

## 📁 Repository Structure

```
dineiq/
├── app.py                          ← Main Streamlit home page
├── requirements.txt
├── README.md
├── .streamlit/config.toml          ← Theme configuration
├── config/
│   └── settings.py                 ← Paths & constants
├── data_generator/
│   └── generate_dataset.py         ← Generates 1M+ records
├── analytics/
│   ├── data_loader.py              ← Cached data loading
│   ├── menu_analysis.py            ← Menu classification
│   ├── customer_segmentation.py    ← RFM + KMeans
│   ├── market_basket.py            ← Apriori rules
│   ├── demand_forecasting.py       ← Ridge regression forecast
│   ├── wastage_analysis.py         ← Wastage + RF risk prediction
│   ├── pricing_analysis.py         ← Price elasticity
│   ├── promotion_analysis.py       ← Effectiveness + trap detection
│   ├── anomaly_detection.py        ← Z-score + IQR anomalies
│   ├── recommendation_engine.py    ← Evidence-based recommendations
│   ├── location_analysis.py        ← Multi-location KPIs
│   ├── peak_analysis.py            ← Peak periods + channels
│   └── dual_pipeline.py            ← Spark vs Python comparison
├── spark_pipeline/
│   └── spark_jobs.py               ← Full PySpark pipeline + MLlib
├── python_pipeline/
│   └── ml_pipeline.py              ← Scikit-learn pipeline
├── pages/                          ← Streamlit multi-page app
│   ├── 1_Executive_Dashboard.py
│   ├── 2_Menu_Intelligence.py
│   ├── 3_Customer_Intelligence.py
│   ├── 4_Wastage_Dashboard.py
│   ├── 5_Forecast_Dashboard.py
│   ├── 6_Dual_Pipeline.py
│   ├── 7_Market_Basket.py
│   ├── 8_Location_Intelligence.py
│   ├── 9_Recommendations.py
│   ├── 10_What_If_Analysis.py
│   ├── 11_Anomaly_Detection.py
│   └── 12_Promotions_Pricing.py
├── utils/
│   └── ui_helpers.py               ← Shared UI components
├── data/
│   ├── raw/                        ← Generated CSV files
│   ├── processed/                  ← Spark output + quality reports
│   └── parquet/                    ← Parquet files
└── models/                         ← Saved ML models (.pkl)
```

## 📊 Dataset Specifications

| Table | Records |
|-------|---------|
| customers | 50,000 |
| restaurants | 20 |
| menu_categories | 12 |
| menu_items | 155 |
| orders | ~120,000 |
| order_items | ~1,100,000 |
| ratings | ~100,000 |
| wastage | ~500,000 |
| pricing_history | ~1,500 |
| promotions | 15 |
| inventory | ~3,100 |

The dataset includes intentional data-quality issues:
- ~1% missing customer IDs
- ~0.5% duplicate orders (prefixed `DUP`)
- Seasonal demand variations
- Rating anomalies (July drops, December floods)
- Misleading promotions (P009: "Flash Blunder")
- High-wastage premium items (M126, M131)
- Price-sensitive items (M148: Truffle Fries)

---


