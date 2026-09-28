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


# Day 1: Data Foundation

**Date:** __24__ / __9__ / 2026
**Goal:** Build the dataset, store it, and ingest it with Spark.

## Tasks

| Member | Task | Files | Status |
|---|---|---|---|
| A | Generate master tables: Customers, Menu_Items, Menu_Categories, Restaurants, Pricing_History | `data_generator/generate_master.py` | [ ] |
| B | Generate transaction tables: Orders, Order_Items, Promotions, Ratings, Inventory, Wastage, with injected defects | `data_generator/generate_transactions.py` | [ ] |
| C | Spark ingestion with explicit schema, schema inference, partitioning, Parquet output | `spark_jobs/01_ingest.py` | [ ] |
| D | Repo structure, README, AI_USAGE.md, DEV_LOG.md, ER diagram, database schema | `database/schema.sql`, `documentation/` | [ ] |

## Dataset Targets

- [ ] 1,000,000+ order-line records
- [ ] 100,000+ orders and 50,000+ customers
- [ ] 150+ menu items across 10+ categories
- [ ] 20+ locations, 12+ months of history
- [ ] 100,000+ ratings, 50,000+ wastage records
- [ ] Defects injected: missing values, duplicates, cancelled orders, invalid prices, negative quantities, anomalies, seasonal and weekend patterns, misleading promotions
- [ ] At least one dataset saved as Parquet

## Suggested Commits

- `chore: initial repo structure and README skeleton`
- `feat: add master data generator`
- `feat: add transaction data generator with defects`
- `feat: add Spark ingestion with explicit schema and Parquet`
- `docs: add ER diagram and DB schema`

## Dev Log (Day 1)

| Item | Notes |
|---|---|
| Work completed | |
| Dataset changes | |
| Data-quality problems | |
| Spark failures | |
| Tests performed | |

## End-of-Day Checklist

- [ ] Every member made at least one commit
- [ ] Dev log updated
- [ ] AI tools used are noted in AI_USAGE.md
- [ ] Everyone can explain their module



# Day 2: Cleaning, Integration and Menu Intelligence

**Date:** __25__ / __SEP__ / 2026
**Goal:** Clean the data, join all tables, engineer features, and classify the menu.

## Tasks

| Member | Task | Files | Status |
|---|---|---|---|
| A | Data quality report and documented cleaning rules | `spark_jobs/02_data_quality.py`, `03_cleaning.py` | [ ] |
| B | Spark SQL / PySpark joins across all tables, feature engineering | `spark_jobs/04_integrate.py`, `05_feature_engineering.py`, `spark_sql/` | [ ] |
| C | EDA (top/lowest sellers, highest profit, high wastage, best/worst rated), menu profitability | `spark_jobs/06_eda.py`, `src/analytics/profitability.py` | [ ] |
| D | Menu classification (Profit Driver, Volume Driver, Hidden Opportunity, Low Performer), tricky cases, web app skeleton | `src/analytics/menu_classification.py`, `src/app.py` | [ ] |

## Checks

- [ ] Data quality report covers: missing values, duplicate orders and order lines, invalid prices, negative quantities, invalid dates and ratings, cancelled orders
- [ ] Every cleaning decision is recorded (remove, fix, or quarantine)
- [ ] Required joins done: orders-customers, orders-items, items-menu, menu-categories, orders-locations, orders-promotions, menu-pricing, menu-ratings, menu-inventory, menu-wastage
- [ ] Features: revenue, cost, margin, profit %, RFM, wastage %, promotion dependency, basket size, price-change %
- [ ] Classification is data-driven, not based on a single hardcoded field
- [ ] Tricky cases handled: high-selling loss-making dish, profitable but rare dish, popular high-wastage dish, new item with little history

## Suggested Commits

- `feat: data quality report`
- `feat: cleaning rules with quarantine table`
- `feat: Spark SQL joins and feature engineering`
- `feat: EDA and menu profitability`
- `feat: menu classification with tricky cases`

## Dev Log (Day 2)

| Item | Notes |
|---|---|
| Work completed | |
| Dataset changes | |
| Data-quality problems | |
| Spark failures | |
| Tests performed | |

## End-of-Day Checklist

- [ ] Every member made at least one commit
- [ ] Dev log updated
- [ ] Cleaned data saved to `processed_data/` and `parquet_data/`
- [ ] Everyone can explain their module


# Day 3: ML Models and Dual Pipeline

**Date:** __26__ / __9__ / 2026
**Goal:** Train Spark MLlib and Python models independently, compare them, and build segmentation and basket analysis.

## Tasks

| Member | Task | Files | Status |
|---|---|---|---|
| A | Spark MLlib: train 3+ algorithms, compare, select and save the final model | `spark_jobs/07_mllib_models.py`, `models/spark/` | [ ] |
| B | Independent Python pipeline (Pandas, Scikit-learn, XGBoost) on the same task and records | `python_pipeline/train_models.py`, `models/python/` | [ ] |
| C | Dual-pipeline comparison on 100+ unseen records | `python_pipeline/compare_pipelines.py`, `reports/` | [ ] |
| D | RFM and customer segmentation, market-basket analysis (support, confidence, lift), bundle recommendations | `src/analytics/segmentation.py`, `basket_analysis.py` | [ ] |

## Checks

- [ ] Data split into train / validation / test
- [ ] Spark: at least 3 algorithms (e.g. Logistic Regression, Random Forest, GBT) with metrics and the final choice justified
- [ ] Python: separate preprocessing and features; accuracy, precision, recall, F1, confusion matrix
- [ ] Spark and Python trained independently, with no predictions copied between pipelines
- [ ] Comparison report has: record ID, actual, Spark result, Python result, match/mismatch, difference, explanation of disagreements, overall agreement %
- [ ] Target: accuracy of 85%+ or macro F1 of 0.80+
- [ ] RFM calculated per customer; segments defined (High-Value Loyal, Frequent, Promotion-Driven, At-Risk, New, Occasional)
- [ ] Basket rules show support, confidence and lift with bundle and cross-sell suggestions

## Suggested Commits

- `feat: Spark MLlib models and model selection`
- `feat: independent Python ML pipeline`
- `feat: dual-pipeline comparison report`
- `feat: RFM and customer segmentation`
- `feat: market-basket analysis`

## Dev Log (Day 3)

| Item | Notes |
|---|---|
| Work completed | |
| Model failures | |
| Spark failures | |
| Spark vs Python agreement % | |
| Tests performed | |

## End-of-Day Checklist

- [ ] Every member made at least one commit
- [ ] Dev log updated
- [ ] Model versions recorded
- [ ] Everyone can explain why the two pipelines disagree where they do


# Day 4: Advanced Analytics and Dashboards

**Date:** __27__ / __9__ / 2026
**Goal:** Finish all analytics modules, the recommendation engine, and the dashboards.

## Tasks

| Member | Task | Files | Status |
|---|---|---|---|
| A | Peak-period analysis, demand forecasting (chronological split), MAE / RMSE / MAPE / R² against a baseline | `src/analytics/peak.py`, `forecasting.py` | [ ] |
| B | Wastage analysis and risk prediction, pricing and price sensitivity, promotion effectiveness and trap detection | `src/analytics/wastage.py`, `pricing.py`, `promotions.py` | [ ] |
| C | Rating and sales anomalies, multi-location comparison, channel analysis, churn risk | `src/analytics/anomalies.py`, `locations.py`, `channels.py`, `churn.py` | [ ] |
| D | Recommendation engine (evidence and priority), what-if analysis, dashboards, filters, CSV/Excel export | `src/analytics/recommendations.py`, `whatif.py`, `src/dashboards/` | [ ] |

## Checks

- [ ] Forecast: training data earlier than test data, no future leakage, configurable forecast period
- [ ] Forecast beats a simple baseline
- [ ] Promotions are not judged on sales increase alone (profit, wastage, repeat purchase also checked)
- [ ] Price-sensitive items classified as High / Moderate / Low
- [ ] Every recommendation shows its evidence and a priority (Low / Medium / High / Critical)
- [ ] What-if outputs are clearly labelled as estimates
- [ ] Dashboards built: Executive, Menu, Customer, Wastage, Forecast, Dual-Pipeline
- [ ] Filters: date, location, item, category, segment, channel, promotion, class, price, rating, wastage
- [ ] Reports download as CSV/Excel; login roles work

## Suggested Commits

- `feat: peak analysis and demand forecasting with time-aware validation`
- `feat: wastage, pricing and promotion analytics`
- `feat: anomaly, location, channel and churn modules`
- `feat: recommendation engine with evidence and priority`
- `feat: what-if analysis and dashboards`

## Dev Log (Day 4)

| Item | Notes |
|---|---|
| Work completed | |
| Dataset changes | |
| Model failures | |
| Performance improvements | |
| Tests performed | |

## End-of-Day Checklist

- [ ] Every member made at least one commit
- [ ] Dev log updated
- [ ] No hard-coded insights or fabricated metrics
- [ ] Everyone can explain their module and modify it on request

# Day 5: Testing, Deployment and Final Deliverables

**Date:** __28__ / __9__ / 2026
**Goal:** Test everything, deploy, and complete all documentation and submission items.

## Tasks

| Member | Task | Files | Status |
|---|---|---|---|
| A | Non-functional checks (response within 5 s, scaling to 5M rows, accuracy targets), hidden-dataset readiness test | `tests/test_nonfunctional.py`, `tests/test_hidden_data.py` | [ ] |
| B | Test cases (functional, integration, data-quality, model, security, boundary), Spark and Python evidence with logs | `tests/`, `reports/evidence/` | [ ] |
| C | Project report with DFD, use case, activity and sequence diagrams; Restaurant Intelligence Report; dual-pipeline report | `documentation/`, `reports/` | [ ] |
| D | Deployment, installation and execution docs, demo video (.mp4), technical blog (2,000+ words), AI_USAGE.md, final checklist | `README.md`, `AI_USAGE.md` | [ ] |

## Hidden-Dataset Readiness

The app must survive data with: missing values, duplicate orders, unknown menu items, new locations, price changes, unusual promotions, extreme wastage, seasonal changes, outliers.

- [ ] Pipeline runs end to end on a freshly generated dataset with a different seed
- [ ] New location and new menu item are handled without code changes

## Surprise Modification Practice

Each member should be able to do one of these live:

- [ ] Add a location
- [ ] Add a menu category
- [ ] Change profitability thresholds
- [ ] Modify the forecast window
- [ ] Add a KPI or an anomaly rule
- [ ] Add a dashboard filter

## Final Submission Checklist

- [ ] Project report
- [ ] Public GitHub URL, with commits from all members on all 5 days
- [ ] Source code, dataset-generation scripts, Parquet data, data dictionary
- [ ] Spark jobs and Spark SQL scripts, MLlib evidence
- [ ] Python model evidence
- [ ] Dual-pipeline comparison report (100+ records)
- [ ] Restaurant Intelligence Report
- [ ] Test cases and results
- [ ] Installation and execution instructions in README.md
- [ ] Deployed URL and evaluator/admin credentials
- [ ] Demo video (.mp4), covering the full pipeline and a difficult contradictory case
- [ ] Technical blog link (2,000+ words)
- [ ] AI_USAGE.md complete (tool, purpose, files, changes, testing, verifier name)
- [ ] Team contribution record and project presentation

## Suggested Commits

- `test: add functional, integration and data-quality tests`
- `test: add hidden-dataset readiness tests`
- `docs: add project report, diagrams and intelligence report`
- `docs: add installation guide, blog and video links`
- `chore: final cleanup and AI_USAGE.md`

## Dev Log (Day 5)

| Item | Notes |
|---|---|
| Work completed | |
| Tests performed and results | |
| Performance results | |
| Bugs fixed | |

