
📊 Power BI Dashboard: Global Superstore Sales Performance
🚀 Project Overview

This project presents a three-page interactive Power BI dashboard designed to analyze global retail sales performance. Built on a highly optimized Star Schema data model, the report ensures scalability, accuracy, and high performance.

The dashboard serves two distinct audiences:

Executives – for a high-level strategic overview

Analysts – for deeper diagnostic detail

It fulfills 20 specific requirements spanning data modeling, DAX measures, advanced visualization, and interactivity.

🛠 Technical Architecture & Data Modeling

The project leverages Power Query (M-Code) to transform a single flat source file into a structured Star Schema, providing a strong foundation for analysis.

🔹 Star Schema Components
Table	Role	Key M-Code Functionality
FactSales	Central fact table holding all transactional data (Sales, Profit, Quantity). Surrogate keys link to dimension tables.	Removed descriptive columns, merged ProductKey, CustomerKey, GeoKey.
DimProduct	Stores product attributes (Category, Sub-Category).	Table.Distinct, created stable ProductKey.
DimCustomer	Stores unique customer details.	Table.Distinct, created stable CustomerKey.
DimGeography	Stores location attributes (Region, State, City).	Table.Distinct, created stable GeoKey.
🔹 Key DAX Measures
Measure	Formula Highlight	Purpose
YoY Sales Growth %	CALCULATE([Total_Sales], SAMEPERIODLASTYEAR(d_date[Date]))	Compares current period with same period last year; vital for executive reporting.
Profit Margin %	DIVIDE(SUM(f_sales[Profit]), [Total_Sales])	Core profitability metric displayed in combo charts.
🗺️ Dashboard Structure & Interactivity

The dashboard is split into three pages, each optimized for specific analytical needs:

1️⃣ Executive Summary (Strategic View)

KPIs: Cards showing Total Sales and YoY Growth % with conditional formatting (green/red).

Trend Analysis: Line chart with drill-down hierarchy (Year → Quarter → Month).

Filters: Chiclet slicer for intuitive filtering by product category.

2️⃣ Detail Analysis (Diagnostic View)

Advanced Charts: Combo chart (Sales, Profit, Margin %) + Small Multiples by Region.

Bookmarks: Toggle between Sales by Region and Sales by Category.

Top N Products: Multi-row card showcasing Top 5 products by sales.

3️⃣ Customer Detail (Entity-Level Drill-through)

Drill-through Functionality: Linked via Customer ID.

User Flow: Right-click any customer on Page 2 → navigate to this page → view that customer’s transaction history (cards & tables auto-filtered).

📸 Dashboard Screenshots

(To be added)

Executive Summary

Detail Analysis

Customer Detail

📂 Project Files

Dashboard.pbix – Final Power BI report file

power_query_m_code.txt – Code snippets for foundational ETL steps
