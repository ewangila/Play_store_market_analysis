# Google Play Store App Market Analysis

**Author:** Eugin Wangila  
**Location:** Nairobi

---

## Overview

**BLUF:** Entering the Android app market requires balancing category saturation, optimal pricing strategies (especially freemium models), and technical constraints (app size and minimum Android versions).  

This project uses **PySpark** to clean and transform raw Google Play Store metadata into an analysis-ready dataset, then surfaces key market insights through an interactive Tableau dashboard. The goal is to support data-driven decisions for a startup’s initial application launch strategy.

---

## Business Problem

Our startup is entering the highly competitive Google Play ecosystem. To maximize visibility and user acquisition we need clear answers to:

- **Category Dynamics** – Which categories deliver the highest installation volumes relative to market saturation?
- **Monetization Impact** – How do free vs paid (and freemium) models influence user acquisition?
- **Technical Constraints** – What role do app size and content maturity ratings play in download success?

---

## Data Understanding

| File | Description |
|------|-------------|
| `data/google_play_store_dataset.csv` | Raw Google Play Store metadata (ratings, size, installs, price, content rating, etc.) |
| `data/google_play_store_cleaned.csv` | Cleaned, analysis-ready dataset produced by the PySpark pipeline |

Key cleaning challenges addressed:
- Duplicate app entries
- String characters (`+`, `,`, `$`) in numeric columns
- Type mismatches and missing values in critical fields (Rating, Installs, Price, Reviews)

---

## Methodology (CRISP-DM)

1. **Business Understanding** – Defined the startup’s core market-entry questions  
2. **Data Understanding** – Explored schema, nulls, and type issues  
3. **Data Preparation** – Deduplicated, cleaned, cast types, and exported a clean CSV  
4. **Data Analysis** – Aggregated category-level performance (installs & average rating)  
5. **Evaluation** – Confirmed data quality and high-level trends  
6. **Deployment** – Published interactive Tableau dashboard

---

## Key Insights (High-Level)

- Categories such as **Communication** and **Games** dominate total installation volume.
- Free / freemium models remain the dominant acquisition engine.
- App size and content rating act as meaningful filters for user download behavior.

*(Full interactive exploration available in the Tableau dashboard below.)*

---

## Interactive Dashboard

[→ Open Google Play Store Market Insights Dashboard](https://public.tableau.com/app/profile/eugin.wangila/viz/GooglePlayStore_17873912896100/GooglePlayStoreAppMarketInsights)

The dashboard includes parameter controls for technical constraints and pricing so stakeholders can dynamically explore viable categories and monetization strategies.

---

## Repository Structure
```
Play_store_market_analysis/
├── data/
│   ├── google_play_store_dataset.csv      # Raw source data
│   └── google_play_store_cleaned.csv      # Cleaned output for Tableau
├── play_store_analysis.ipynb              # Full PySpark cleaning + analysis notebook
├── requirements.txt                       # Python dependencies
├── LICENSE                                # MIT License
├── .gitignore
└── README.md                 
```
## How to Reproduce

### 1. Clone the repository
```
bash
git clone https://github.com/ewangila/Play_store_market_analysis.git
cd Play_store_market_analysis
```
### 2. Prerequisites

- Python 3.8+
- Apache Spark / PySpark
- Jupyter Notebook (or JupyterLab)
- Optional: Tableau Public / Desktop (to open the published dashboard)

### 3. Run the analysis
```
bash
jupyter notebook play_store_analysis.ipynb
```
## The notebook will:

1. Load the raw dataset  
2. Clean and transform the data with PySpark  
3. Export `data/google_play_store_cleaned.csv`  
4. Generate initial category performance visualizations  

---

## Technologies Used

- **PySpark** – Distributed data cleaning & aggregation  
- **Pandas** – Intermediate conversion for export  
- **Matplotlib & Seaborn** – Notebook visualizations  
- **Tableau Public** – Interactive dashboard deployment  

---

## License

This project is licensed under the MIT License.

**Author:** Eugin Wangila  
**Location:** Nairobi
