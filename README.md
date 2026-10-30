# DAX-And-Data-Visualization
# E-Commerce Sales Analysis using Power BI

## 📊 Project Overview

This project focuses on analyzing e-commerce sales data using **Microsoft Power BI**. The objective is to transform raw sales data into meaningful business insights using data modeling, DAX (Data Analysis Expressions), and interactive visualizations.

The dashboard provides insights into sales performance, profitability, order trends, sales target achievement, and geographical distribution.

## 🎯 Project Objectives

- Analyze overall e-commerce sales performance.
- Calculate key business metrics using DAX.
- Compare actual sales against sales targets.
- Identify profitable product categories and sub-categories.
- Analyze monthly sales trends.
- Understand sales performance across different cities and states.
- Create interactive and visually appealing Power BI dashboards.

## 📁 Dataset Description

The project uses three CSV files:

| Dataset | Description |
|---|---|
| List of Orders.csv | Contains order information, including order ID, order date, customer details, city, and state. |
| Order Details.csv | Contains order-level details such as amount, profit, quantity, category, and sub-category. |
| Sales target.csv | Contains monthly sales targets for different product categories. |

## 🛠️ Tools & Technologies

- Microsoft Power BI
- Power Query Editor
- DAX (Data Analysis Expressions)
- Data Modeling
- CSV Datasets
- Data Visualization

## 🔗 Data Modeling

Before creating visualizations, relationships were established between the three tables.

The data model connects:
- **List of Orders** and **Order Details** using Order ID.
- **Sales Target** and the relevant sales category/date dimensions using Category and Month, based on the available dataset structure.

A proper data model ensures accurate calculations and meaningful analysis.

## 🧮 DAX Calculations

### 1. Calculated Columns

**Category Type**

Category Type = CONCATENATE('Order Details'[Category], CONCATENATE(" - ", 'Order Details'[Sub-Category]))

**Revenue per Order**

Revenue per Order = 'Order Details'[Amount]*'Order Details'[Quantity]

**Sales Category**

Sales Category = IF('Order Details'[Amount] > AVERAGE('Order Details'[Amount]), "Above Average", "Below Average")

### 2. Calculated Measures

**Order Count**

Number of Order = COUNT('Order Details'[Order ID])

**Average Profit in Delhi**

Avg Profit Delhi = CALCULATE(AVERAGE('Order Details'[Profit]),FILTER('List of Orders', 'List of Orders'[City]="Delhi"))

**Year-to-Date (YTD) Sales**

YTD Sales = TOTALYTD(SUM('Order Details'[Amount]), 'List of Orders'[Order Date])

*Note: A dedicated Date table is recommended for accurate time-intelligence calculations.*

## 📈 Dashboard Visualizations

| Visualization | Chart Type | Purpose |
|---|---|---|
| Sales Target Achievement by Category | Clustered Column Chart | Compares actual sales with sales targets by category. |
| Max Profit Margin by Sub-Category | Donut Chart | Displays maximum profit margin across sub-categories. |
| Monthly Sales Trend | Line Chart | Analyzes monthly sales performance over time. |
| Profit vs Quantity by Sub-Category | Scatter Chart | Identifies the relationship between profit and quantity sold. |
| Total Sales Amount vs Target | Card Visuals | Displays total actual sales and sales targets. |
| Minimum Target by Segment | Multi-row Card | Displays minimum sales targets across segments. |
| Sales Performance Matrix | Matrix | Compares actual sales and targets across categories and months. |
| Geographic Sales Analysis | Map | Shows sales distribution across different cities. |
| Sales Distribution by Sub-Category | Treemap | Represents sales contribution by sub-category. |
| Order Count by State | Funnel Chart | Visualizes order count distribution across different states. |

## 🔍 Key Analysis Areas

- **Sales Performance:** Actual sales compared with predefined targets.
- **Profitability:** Profit margins across product categories and sub-categories.
- **Sales Trends:** Monthly and yearly sales patterns.
- **Product Analysis:** Sales and quantity distribution across sub-categories.
- **Geographical Insights:** Sales performance across cities and states.
- **Business Performance:** Order count and target achievement.

## 💡 Skills Demonstrated

- Data Cleaning and Transformation
- Data Modeling and Relationships
- Calculated Columns and Measures
- DAX Functions and Time Intelligence
- Sales and Profitability Analysis
- Interactive Dashboard Development
- Data Visualization and Business Intelligence

## 🚀 Conclusion

This project demonstrates how Power BI can be used to transform raw e-commerce sales data into actionable business insights.

By combining data modeling, DAX calculations, and interactive visualizations, the project provides a comprehensive view of sales performance, profitability, product trends, and geographical sales distribution.

---

**Project:** E-Commerce Sales Analysis  
**Tool:** Microsoft Power BI  
**Domain:** E-Commerce / Business Intelligence
