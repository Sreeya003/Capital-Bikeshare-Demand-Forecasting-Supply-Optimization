# Capital Bikeshare Demand Forecasting & Supply Optimization

## 📊 Project Overview
This project addresses the "Availability Crisis" in urban transit by developing a high-precision forecasting engine for the **Capital Bikeshare system in Washington, D.C.**. By analyzing 17,544 hourly observations (2011–2012), this study transitions from a reactive operational model to a proactive, data-driven supply strategy.

## 🚀 Key Results
* **Best Model:** XGBoost with engineered lag features.
* **Accuracy:** Achieved a **MAPE of 23.75%**, a **77.6% improvement** over the ARIMA baseline.
* **Impact:** Developed a 30-day proactive supply plan for January 2013 with a **15% risk-mitigation buffer**.

## 🛠️ Tech Stack
* **Language:** R
* **Libraries:** `xgboost`, `prophet`, `forecast`, `tidyverse`, `zoo`, `tsibble`
* **Techniques:** Time Series Decomposition (STL), Linear Interpolation, Feature Engineering (Lags/Rolling Means), Hyperparameter Tuning.

## 📈 Methodology

### 1. Data Engineering (The "Sandy Solution")
* **Integrity Audit:** Identified 165 missing records clustered around "shocks" like **Hurricane Sandy** and major winter storms.
* **Resilient Imputation:** Utilized **linear interpolation** to repair structural gaps, preserving the near-zero ridership reality of system shutdowns while maintaining temporal continuity for ML training.

### 2. Exploratory Data Analysis (EDA)
* **Behavioral Split:** Identified a bimodal weekday pattern (commuter spikes at 8 AM/5 PM) and a unimodal weekend plateau (leisure peak 12 PM–3 PM).
* **Weather Drivers:** Quantified a non-linear **inverted-U relationship** between temperature and demand, peaking at 25°C.

### 3. Predictive Modeling
* **Battle of the Models:** Staged a competition between six frameworks: Seasonal Naive, Holt-Winters, ARIMA, TBATS, Prophet, and XGBoost.
* **Winning Engine:** XGBoost outperformed all models by effectively capturing non-linear environmental drivers and historical "memory" via **1, 7, and 30-day lag features**.

## 📋 Operational Strategy (January 2013)
* **Supply Plan:** Generated a daily redistribution blueprint featuring a **15% safety buffer** to eliminate "stock-outs" during demand surges.
* **Maintenance Window:** Identified **3:00 AM – 4:00 AM** as the optimal window for station rebalancing with zero service disruption.
