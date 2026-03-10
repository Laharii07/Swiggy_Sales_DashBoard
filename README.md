# 🍽️ Swiggy Sales Analysis Dashboard

An interactive and dynamic Excel dashboard built to analyze real-time Swiggy food delivery transactions across India, enabling business owners and stakeholders to evaluate profitability, track operational trends, and make data-driven decisions.

---

## 📌 Business Problem

Food delivery networks need insights into how time, geography, and customer preferences affect order demand and revenue. This project analyzes real-time Swiggy transaction data to identify purchasing patterns that help optimize promotional planning, manpower allocation, and overall business profitability.

---

## 📂 Project Structure

```
swiggy-sales-dashboard/
│
├── data/
│   └── swiggy_data.xlsx          # Raw transaction dataset (~197K records)
│
├── dashboard/
│   └── swiggy_dashboard.xlsx     # Final Excel workbook containing:
│       ├── Sheet 1: Swiggy Data  # Raw data + engineered columns
│       ├── Sheet 2: Analysis     # Pivot Tables, KPI calculations, data extraction
│       └── Sheet 3: Dashboard    # Interactive frontend UI & visualizations
│
└── README.md                     # Project documentation
```

---

## 📊 Dataset Description

| Property | Details |
|---|---|
| **Source** | Real-time Swiggy Transactions Dataset |
| **Rows** | ~197,000 order records |
| **Columns** | 10 original + 4 engineered features |
| **Period** | January – August 2025 |

**Key Variables:**
- `State` & `City`
- `Order Date`
- `Restaurant Name` & `Location`
- `Category`
- `Dish Name`
- `Price`
- `Rating`
- `Rating Count`

**Engineered Features:**
- `Food Type` — Veg / Non-Veg (keyword-based classification)
- `Day` — 3-letter day initial extracted from Order Date
- `Quarter` — Financial quarter (Q1, Q2, Q3)
- `Week` — Week number of the year

---

## 🧹 Data Cleaning & Preparation

- Verified no missing or blank values across key columns
- Converted raw data range into a dynamic Excel Table format
- Corrected auto-formatted Week column from Date type to Number
- Extracted Day name and Quarter from the Order Date column
- Standardized all numerical fields to consistent formatting

---

## ⚙️ Feature Engineering

| Feature | Formula / Logic |
|---|---|
| **Food Type** | `IF + OR` scanning Dish Name for keywords → Veg / Non-Veg |
| **Day** | `TEXT(Order Date, "ddd")` → Sun, Mon, Tue, etc. |
| **Quarter** | `INT((MONTH(Order Date) + 2) / 3)` concatenated with "Q" → Q1, Q2, Q3 |
| **Week** | `WEEKNUM(Order Date)` → numerical week of the year |

**Non-Veg Keywords:** chicken, mutton, egg, fish, prawns, etc.

---

## 📈 Key Findings & Business Insights

- Order demand peaks on **weekends (Sat & Sun)**; lowest on Mon & Tue
- **January** records the highest sales (₹6.8M+); February is the weakest month
- **Vegetarian orders dominate** with 64% of total sales share
- **Bangalore** is the top revenue city, followed by Lucknow, Hyderabad, Mumbai, and New Delhi
- **Karnataka, Uttar Pradesh, and Maharashtra** lead in state-level sales
- States lacking metro hubs **(J&K, Nagaland, Assam)** record the lowest sales
- Quarterly performance shows a **flat trend** with no significant growth across Q1–Q3

---

## 📉 Overall KPIs

| Metric | Value |
|---|---|
| Total Orders | 197K+ |
| Total Sales | ₹53M |
| Average Order Value (AOV) | ₹268 |
| Average Rating | 4.34 |

---

## 📊 Dashboard Overview

An interactive Excel dashboard with the following sections:

- **High-Level KPIs** — Total Sales, AOV, Ratings, Total Orders
- **Monthly, Weekly & Daily Sales Trends**
- **Geographical Sales** — by State (Map Chart) & Top 5 Cities
- **Veg vs Non-Veg** Food Preference Analysis
- **Quarterly Performance** Summary Grid
- **Interactive Slicers** — filter by Month, Restaurant Name, Category
- **Sheet Navigation Buttons** — Dashboard / Analysis / Data

<img width="1857" height="615" alt="DashBoard" src="https://github.com/user-attachments/assets/af1c494d-9a9b-4535-8e57-f7e106619aea" />

---

## 🛠️ Tools & Technologies

**Primary Tool:** Microsoft Excel

**Excel Features Used:**
- Pivot Tables & Pivot Charts
- `IF`, `OR`, `TEXT`, `INT`, `MONTH`, `WEEKNUM` functions
- `GETPIVOTDATA` for dynamic KPI extraction
- Custom Number Formatting (₹, K, M suffixes)
- Shapes, Text Boxes & Linked Pictures for dashboard UI
- Slicers for interactive filtering
- Map Charts for geographical visualization

**Industry Alternatives:** Power BI · Tableau · Python · SQL · QlikSense · Google Looker Studio

---

## ✅ Recommendations

- Increase delivery manpower during **weekends and peak months** (January, May, August)
- Run **targeted discounts** on Mondays, Tuesdays, and slow months (February, June)
- Prioritize **operational expansion** in metro cities and IT hubs (Bangalore, Lucknow, Hyderabad)
- Introduce **aggressive growth strategies** to break the flat quarterly sales trend
- Heavily promote **vegetarian options** to capitalize on the 64% majority food preference

---

## ⚠️ Limitations

- Map Charts cannot be generated directly from Pivot Tables
- Geographical map rendering requires an active internet connection
- Dashboard KPIs cannot be linked directly to Pivot Table cells
- Excel performance degrades with ~197K rows and multiple Pivot Tables
- Dataset is limited to January–August 2025, restricting full-year analysis
- Customer demographics and delivery time data are not captured

---

## 🚀 Future Improvements

- Migrate dashboard to **Power BI** for more robust and scalable analysis
- Implement advanced **DAX functions** and measures for deeper calculations
- Incorporate additional data points — delivery time, customer demographics, return order rates
- Push targeted promotions during low-performing periods (February, Mondays, Tuesdays)
- Introduce growth strategies to break the stagnant quarterly sales flat line

---
