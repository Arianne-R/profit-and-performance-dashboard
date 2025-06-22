# Profit and Performance Dashboard

![Made with Power BI](https://img.shields.io/badge/Made%20with-Power%20BI-f2c811?logo=powerbi&logoColor=black&style=flat)
![Data Cleaning](https://img.shields.io/badge/Data-Cleaning-brightgreen?style=flat)
![DAX Calculations](https://img.shields.io/badge/DAX-Calculated%20Metrics-blue?style=flat)
![Interactive Dashboard](https://img.shields.io/badge/Interactive-Dashboard-blueviolet?style=flat)

## Overview

This Power BI project delivers a **Profit and Performance Dashboard** designed to convert raw data into actionable business insights. It demonstrates a full analytics workflow — from **data preparation and transformation** through **DAX-based calculations** to **intuitive dashboard design**.

The dashboard offers a comprehensive view of profit trends, product and segment profitability, country-level performance, and key financial metrics. Its clean and interactive visuals are tailored to empower stakeholders with clear, data-driven decision-making.

---

## Project Objectives

- Clean and model raw data using Power Query and DAX.
- Build a date dimension table to enable time intelligence.
- Create measures and KPIs for tracking profitability and revenue.
- Design a professional, interactive dashboard suitable for business reporting.
- Communicate key insights using data storytelling techniques.

---

## Dataset

- `raw_data.xlsx` — Original raw sales and financial data used for analysis.  
- `profit_and_performance_dashboard.pbix` — Power BI project file containing all data models, measures, and report visuals.  
- `dashboard_preview.PNG` — Image snapshot capturing the main dashboard layout and key performance indicators.
## Project Files

The following files are included in this project for demonstration and portfolio purposes:

- <a href="https://github.com/Arianne-R/road-accident-dashboard/blob/main/road_accident_raw_data.xlsb">**raw_data.xlsx**</a> – Contains the original raw sales and financial data used for analysis. 
- <a href="https://github.com/Arianne-R/road-accident-dashboard/blob/main/road_accident_dashboard.xlsb">**profit_and_performance_dashboard.pbix**</a> – Power BI project file containing all data models, measures, and report visuals.
- <a href="https://github.com/Arianne-R/road-accident-dashboard/blob/main/dashboard_preview.png">**dashboard_preview.png**</a> – Image snapshot capturing the main dashboard layout and key performance indicators.

---

## Data Preparation & Cleaning

- Verified data quality; ensured all columns were 100% valid with no errors or blanks.  
- Converted key financial columns (e.g., Sales, Profit, COGS) to *Fixed Decimal Number* for accurate calculations.  
- Reformatted the Date column using the locale `English (United States)` to standardize date parsing.  
- Renamed `Month Name` column to `Month` for easier reference in analysis.

---

## Data Modeling & DAX

### DAX Measure
- Created key measure using DAX:
```DAX
Gross Profit Margin % = DIVIDE(SUM(Financials[Profit]), SUM(Financials[ Sales]), 0)
```

### Calendar Table

- Created a calendar table **dCalendar** for time intelligence spanning 2013 to 2014 using DAX:  
 ```DAX
 dCalendar = CALENDAR(DATE(2013,01,01), DATE(2014,12,31))
```

- Established an active one-to-many relationship between `dCalendar[Date]` and `Financials[Date]`.

### Additional Calendar Columns

To enable proper month/year slicers and sorting:
Year = YEAR(dCalendar[Date])
Month = FORMAT(dCalendar[Date], "Mmm")
MonthNumber = MONTH(dCalendar[Date])

- Sorted the Month column by MonthNumber to ensure correct month order in visuals.

---

## Dashboard Features

### KPI Cards
- **Total Profit**
- **Gross Profit Margin %**
- **Total Revenue** (renamed from Sales)
- **Total Units Sold**

### Profit Trend by Month (Line Chart)
- **X-axis:** Month from dCalendar
- **Y-axis:** Total Profit

### Profit by Product (Clustered Column Chart)
- **X-axis:** Product
- **Y-axis:** Total Profit

### Profit by Segment (Clustered Bar Chart)
- **X-axis:** Total Profit
- **Y-axis:** Segment

### Profit Share by Country (Donut Chart)
- **Values:** Total Profit
- **Legend:** Country

### Performance by Country (Matrix Table)
- **Metrics:** Revenue, Profit, Gross Profit Margin %, Units Sold

### Interactive Slicers
- **Fields:** Year, Month from dCalendar

---

## Key Insights Summary

- Profit peaks occur in **October** and **December**, hinting at seasonality in sales trends.
- **Paseo** is the top product (~$4.80M profit), while **Carretera** underperforms.
- **Government** segment is the most profitable (~$11M), suggesting strong B2G opportunities.
- **Enterprise** segment shows losses, indicating a need for strategic review.
- **France** leads in profit share (22.38%), making it a key growth market.
- **USA** generates the highest revenue but has the lowest margin (11.97%), signaling inefficiency.

> These insights are based on the full dataset with no slicer filters applied. Filtered results may yield different conclusions.

---

## How to Use
1. Open `profit_and_performance_dashboard.pbix` in Power BI Desktop.  
2. Ensure locale settings match (English - United States) if needed.  
3. Use Year and Month slicers to explore time-based trends.  
4. Hover over visuals or read insight boxes for commentary.

---

## Tools & Skills Demonstrated

| Skill / Tool          | Description                                   |
|-----------------------|-----------------------------------------------|
| Power BI Desktop      | Data modeling, visuals, and DAX measures     |
| Power Query Editor    | Data cleaning and transformation              |
| DAX                   | Measures and calculated columns               |
| Data Visualization    | KPI cards, charts, matrix, and conditional formatting |
| Business Analysis     | Identifying strategic insights from data      |
| Storytelling with Data| Added narrative explanations and contextual insights |

---

## Dashboard Preview

![dashboard_preview](https://github.com/user-attachments/assets/5d8baa05-2c0e-4fff-bc4d-80be8bbd14d6)


> Dashboard snapshot illustrating key financial KPIs and trends, designed for clear and concise executive reporting.

---

## Explore the Dashboard

This Profit and Performance Dashboard allows you to explore key financial metrics across time periods, products, customer segments, and regions. Use the **Year** and **Month** slicers to filter data dynamically and uncover trends or anomalies. The dashboard’s clean and intuitive design helps you easily analyze performance, identify opportunities, and support data-driven decision-making.

For questions or further discussion, please don’t hesitate to connect with me via LinkedIn (link available in my GitHub profile).
