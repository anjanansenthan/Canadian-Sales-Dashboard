Canadian Sales Performance Dashboard

Interactive Power BI dashboard analyzing sales performance across Canadian regions and product categories, built with Power Query, DAX measures, and a star schema data model.

Overview

This project explores sales trends, regional performance, and product category breakdowns using a retail sales dataset. It was built end-to-end — from raw CSV data to a polished, multi-page interactive report — as a portfolio piece demonstrating Power BI skills for data analysis roles.

Screenshots

Overview Page Show Image

Products Page Show Image

Details Page Show Image

Tools Used
Power BI Desktop — report building and data modeling
Power Query (M) — data import, cleaning, and transformation
DAX — calculated measures and time intelligence
What's Inside

Data model: A star schema with Sales as the fact table, related to two dimension tables — Products and Customers — via one-to-many relationships.

Key DAX measures:

Total Sales = SUM(Sales[LineTotal])
Total Quantity = SUM(Sales[Quantity])
Order Count = DISTINCTCOUNT(Sales[OrderID])
Average Order Value = DIVIDE([Total Sales], [Order Count])
Total Sales (All Regions) = CALCULATE([Total Sales], ALL(Customers))
Electronics Sales = CALCULATE([Total Sales], Products[Category] = "Electronics")
Sales YTD = TOTALYTD([Total Sales], Sales[Date])

Report pages:

Overview — KPI cards (Total Sales, Total Quantity, Order Count, Average Order Value) and a monthly sales trend line chart
Products — sales broken down by category (bar chart) and a region × category matrix
Details — raw order-level data table for drilling into specifics

Interactivity: A Region slicer synced across all pages, so filtering by province updates every visual in the report simultaneously.

Data

Sample retail sales data covering 400 orders across 12 products and 25 customers spanning five Canadian provinces (Ontario, Quebec, British Columbia, Alberta, Manitoba). Located in /data.

Next Steps
Add drill-through from the Overview chart directly into the Details page
Expand time intelligence (MoM, YoY comparisons)
Rebuild with a larger, real-world dataset
Files
├── data/                  # Source CSV files
├── screenshots/           # Report page screenshots
├── SalesDashboard.pbix    # Power BI project file
└── README.md
