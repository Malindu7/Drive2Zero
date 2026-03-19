# ⚡ Drive2Zero
### Forecasting Sri Lanka's Transport CO₂ Emissions & EV Adoption

> **Data Odyssey 2025** · AI and Data Science Club · General Sir John Kotelawala Defence University

[![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange?logo=jupyter)](https://jupyter.org)
[![PowerBI](https://img.shields.io/badge/Dashboard-Power%20BI-yellow?logo=powerbi)](https://powerbi.microsoft.com)
[![SDG11](https://img.shields.io/badge/SDG-11%20Sustainable%20Cities-orange)](https://sdgs.un.org/goals/goal11)
[![SDG13](https://img.shields.io/badge/SDG-13%20Climate%20Action-green)](https://sdgs.un.org/goals/goal13)

---

## 🌏 Overview

Sri Lanka had over **8.3 million registered vehicles** by 2020, with the transport sector becoming one of the country's largest contributors to greenhouse gas emissions. Globally, transport accounts for **nearly 23% of energy-related CO₂ emissions**.

**Drive2Zero** is a data science and AI platform that:
- 📊 Analyses Sri Lanka's vehicle registration trends (2008–2023)
- 🔮 Forecasts future transport CO₂ emissions using ARIMA time-series modelling
- ⚡ Simulates the impact of different EV adoption scenarios through to 2040
- 📈 Visualises policy-ready insights through an interactive Power BI dashboard

---

## 👥 Team — Tech Wizards 2.0

| Name | Index No. |
|---|---|
| JAC Sudarshika | D/DBA/23/0011 |
| OM Kavishan | D/DBA/23/0012 |
| SAHI Piyathilaka | D/DBA/23/0031 |
| KKASCW Bandara | D/DBA/23/0037 |

---

## 📁 Project Structure

```
Drive2Zero/
│
├── 📓 Drive2Zero_Final.ipynb        ← Main analysis notebook (Python)
│
├── data/
│   └── new_vehicles_registered_2008-2023.xlsx   ← Source: Department of Motor Traffic
│
├── docs/
│   ├── Drive2Zero_Technical_Document.docx   ← Explanation
│   └── Script_2.txt                    ← Video narration script
│
├── dashboards/
│   ├── new2026.pbix   ← new dashboard
│ 
|
└── README.md
```

---

## 🔬 Methodology

### Data Sources
- **Local:** Vehicle registration statistics — Sri Lanka Department of Motor Traffic (2008–2023)
- **Global:** CO₂ emission data — Our World in Data (OWID), IEA energy profiles
- **Emission factors:** IPCC AR6 Working Group 3 Tier 1 factors

### Pipeline

```
Raw Excel Data  →  Preprocessing  →  EDA  →  CO₂ Estimation  →  ARIMA Forecast  →  EV Simulation  →  Dashboard
```

1. **Data preprocessing** — Cleaned `-` and missing values, reshaped from wide to long format, categorised vehicle classes and fuel types
2. **CO₂ estimation** — Applied IPCC Tier 1 emission factors per vehicle class × fuel type × average annual km
3. **ARIMA forecasting** — ADF stationarity test → log-differencing → grid search (p,d,q) → forecast 2024–2040 with 90% confidence intervals
4. **EV scenario simulation** — S-curve (logistic) adoption model across 5 scenarios (BAU to 80% EV), with improving grid emission factor as renewables grow
5. **Model validation** — Hold-out test on 2020–2023, MAE/RMSE/MAPE metrics, Random Forest and Gradient Boosting benchmarks

### EV Adoption Scenarios

| Scenario | EV Share by 2040 | CO₂ Reduction vs BAU |
|---|---|---|
| Baseline (BAU) | ~2% | — |
| Low EV | 15% | ~12% |
| Medium EV | 30% | ~22% |
| High EV | 50% | ~35% |
| Full EV | 80% | ~55% |

---

## ⚙️ How to Run

### Python Notebook

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/Drive2Zero.git
cd Drive2Zero

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn openpyxl ipywidgets

# 3. Launch Jupyter
jupyter notebook Drive2Zero_Notebook.ipynb
```

> Place `new_vehicles_registered_2008-2023.xlsx` in the same directory as the notebook.

### R Script

```r
# Install required packages
install.packages(c("readxl","dplyr","tidyr","stringr","zoo","forecast","ggplot2","tseries"))

# Run the script
source("drive2zero_analysis.R")
```

### Power BI Dashboards
Open `.pbix` files in **Power BI Desktop** (free download from Microsoft). The dashboards include:
- Vehicle registration trends and fleet composition
- Historical and projected CO₂ emissions by fuel type and vehicle class
- Interactive EV adoption scenario simulator with sliders
- EV barrier analysis and policy recommendation visualisation

---

## 📌 Key Findings

- Sri Lanka's vehicle registrations peaked in **2015–2016**, collapsed during COVID-19, and are recovering
- **EV adoption is currently ~1.8%** of new registrations — very low but growing
- A **High EV (50%) scenario** by 2040 could reduce transport CO₂ by ~35% vs baseline
- **Motorcycles dominate** (~80% of new registrations) — electrifying this segment offers the biggest impact

### Main Barriers to EV Adoption
- High purchase costs compared to conventional vehicles
- Limited charging infrastructure (mostly urban)
- Pressure on electricity grid
- Frequent policy and tax changes

### Policy Recommendations
1. Reduce import duties and provide EV purchase subsidies
2. Expand charging network beyond cities
3. Grow grid renewable capacity (amplifies EV emission benefits)
4. Establish stable, long-term EV policy framework
5. Prioritise electrification of motorcycles and three-wheelers

---

## 🎯 SDG Alignment

| Goal | Contribution |
|---|---|
| **SDG 11** — Sustainable Cities and Communities | Reduces urban air pollution and congestion in Colombo |
| **SDG 13** — Climate Action | Provides data-driven tools supporting Sri Lanka's 2050 carbon neutrality target |

---

## 📚 References

1. IPCC AR6 Working Group 3 — https://www.ipcc.ch/report/ar6/wg3/chapter/
2. Lanka Statistics — Registered Motor Vehicles — https://lankastatistics.com/social/registered-motor-vehicles.html
3. Our World in Data — CO₂ Emissions — https://ourworldindata.org/co2-emissions
4. International Energy Agency — Sri Lanka Energy Profile

---

*Data Odyssey 2025 · General Sir John Kotelawala Defence University · AI and Data Science Club*
