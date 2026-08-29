📌 Overview

This project transforms raw pizza order data (orders, order details, pizzas, and pizza types) into a single, interactive business intelligence dashboard. It combines data cleaning, table relationships, calculated fields, and DAX-driven KPIs to answer real business questions — which products sell best, when demand peaks, and how revenue trends over time.

🎯 Objectives
Track overall sales performance: total sales, total pizzas sold, total orders, and average ticket size
Monitor monthly and yearly revenue trends
Analyze sales by pizza category (Chicken, Classic, Supreme, Veggie)
Analyze sales by pizza size (S, M, L, XL, XXL)
Identify peak ordering hours to support staffing and kitchen planning
Rank top-performing pizzas by revenue and quantity sold
Build a clean, relational data model connecting orders, order details, pizzas, pizza types, and a calendar table
🛠️ Tech Stack
Category	Tools
Data Modeling & Dashboard	Power BI Desktop
Data Transformation (ETL)	Power Query Editor
Calculations	DAX
Source Data	CSV (Orders, Order Details, Pizzas, Pizza Types)
🗂️ Data Model

A star-schema model connects the fact table (order_details) to dimension tables orders, pizzas, pizza_types, and a custom calender table for time-based analysis.

Show Image

Table	Purpose
orders	Order-level date and hour information
order_details	Line-item level data — order_id, pizza_id, quantity
pizzas	Pizza-level data — pizza_id, pizza_type_id, size, price
pizza_types	Pizza master data — category, ingredients, name
calender	Date dimension — month, month number, quarter, week of year
🔄 ETL Process (Power Query)

Raw CSV order data was cleaned and enriched entirely in Power Query Editor before loading into the model:

Source / Navigation — Connected to the raw order-details CSV
Promoted Headers / Changed Type — Set correct data types for all key columns
Merged Queries — Merged order_details with pizzas to bring in size and price
Expanded pizzas — Expanded pizzas.size and pizzas.price into order_details
Added Custom Column — Created an amount column (quantity × price) for revenue calculations
Changed Type — Formatted amount as Currency

Show Image

📊 Dashboard Highlights
KPI	Value
Total Sales	₹1M
Pizzas Sold	87K
Total Orders	85K
Avg. Ticket Size	₹16.63
Monthly Revenue	₹112K
Yearly Revenue	₹1M

Key visuals include:

🍕 Category-wise sales donut chart (Chicken, Classic, Supreme, Veggie)
📏 Size-wise order distribution pie chart (S, M, L, XL, XXL)
⏰ Peak ordering hours line chart
📈 Monthly sales trend line
📅 Yearly order distribution bar chart
🏆 Top-performing pizzas table by amount & quantity sold
🎛️ Category filter buttons for interactive slicing

Show Image

💡 Key Insights
A small set of premium pizzas (Classic Deluxe, Big Meat, Four Cheese) drive a disproportionate share of revenue
Order volume peaks sharply around a specific hour of the day — useful for staffing decisions
Medium and Large sizes account for the majority of orders over Small and XL/XXL
Monthly revenue fluctuates within a fairly tight ₹111K–₹127K range, indicating stable demand
📁 Repository Structure
├── img/                          # Dashboard & documentation screenshots
├── Dominos_Pizza_Analytics_Documentation.pdf   # Full project documentation
├── Dominos_Pizza_Analytics_Documentation.docx  # Editable documentation
└── README.md
📄 Full Documentation

For a detailed breakdown of the data model, ETL steps, DAX measures, and business analysis, see the full project documentation.

Author: MD Sahil 📧 sahilmansoor024@gmail.com | LinkedIn | Portfolio
