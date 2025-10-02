# PowerBI-StarSchema-Sales-Dashboard
A multi-page Power BI dashboard built on a Star Schema model for retail sales analysis.

🚀 Project Overview
This project delivers a comprehensive, three-page interactive Power BI dashboard designed to analyze retail sales performance. The report is built on a highly optimized Star Schema data model, ensuring high performance and scalability.

The dashboard effectively caters to two distinct audiences: Executives (strategic overview) and Analysts (diagnostic detail), fulfilling 20 specific requirements related to data modeling, DAX measure creation, advanced visualization, and interactivity.

🛠 Technical Architecture and Data Modeling
The foundation of this project is a robust data model, transforming a single, flat source file into a structured Star Schema.

Star Schema Components:
Table

Role

Key M-Code Functionality

FactSales

Transactional data, containing all key performance metrics (Sales, Profit, Quantity) and Surrogate Keys.

Removed all descriptive columns and merged in ProductKey, CustomerKey, and GeoKey.

DimProduct

Stores unique product attributes (Category, Sub-Category).

Used Table.Distinct and created a stable ProductKey.

DimCustomer

Stores unique customer details.

Used Table.Distinct and created a stable CustomerKey.

DimGeography

Stores unique location data (Region, State, City).

Used Table.Distinct and created a stable GeoKey.

Key DAX Measures
The analytical capabilities are driven by Time Intelligence DAX, leveraging the defined date relationship:

Measure

Formula Highlight

Purpose

YoY Sales Growth %

CALCULATE([Total_Sales], SAMEPERIODLASTYEAR(d_date[Date]))

Compares current period performance against the same period one year prior, essential for executive reporting.

Profit_Margin %

DIVIDE(SUM(f_sales[Profit]), [Total_Sales])

Core profitability metric used in the Combo Chart.

🗺️ Multi-Page Dashboard Structure & Interactivity
The report is segmented to optimize the user experience and analytical flow.

Page 1: Executive Summary (Strategic View)
KPIs: Prominent Total Sales and YoY Growth % card with Conditional Formatting (Green/Red).

Trend: Line Chart displaying Sales trend with Drill-down Hierarchy (Year → Quarter → Month).

Filters: Utilizes a Chiclet Slicer for intuitive filtering by Category.

Page 2: Detail Analysis (Diagnostic View)
Advanced Charts: Features a Combo Chart (Sales, Profit, Margin %) and a sales breakdown using Small Multiples by Region.

Bookmarks: Implemented two bookmarks to allow analysts to toggle the main visual between Sales by Region and Sales by Category views.

Top N: Includes a Multi-row Card showcasing the Top 5 Products by Sales.

Page 3: Customer Detail (Entity-Level Drill-through)
Functionality: This page is set as the Drill-through target using the Customer ID field.

User Flow: Analysts can right-click any customer in a summary visual on Page 2 and navigate directly here, instantly filtering all cards and tables to that single customer's transaction history.

📸 Dashboard Screenshots

Executive Summary

Detail Analysis

Customer Detail







📂 Project Files
Dashboard.pbix: The final Power BI report file.

dax_measures.txt: Code snippets for key DAX formulas.

power_query_m_code.txt: Code snippets for the foundational ETL steps.
