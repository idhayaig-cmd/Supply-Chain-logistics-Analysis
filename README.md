# 📦 Supply Chain & Logistics Analysis (Power BI Project)

## 📌 Project Overview
This project focuses on analyzing and optimizing supply chain operations for a retail logistics company. It evaluates key areas such as procurement, inventory, transportation, and order fulfillment to improve efficiency and reduce operational costs.

The solution leverages **Excel, Power Query, and Power BI** to deliver interactive dashboards and actionable business insights.

---

## 🎯 Project Objectives
- Analyze key supply chain KPIs:
  - Delivery Time
  - Transportation Cost
  - Inventory Levels
  - Order Fulfillment Rate
- Identify inefficiencies and bottlenecks in logistics operations
- Improve demand forecasting and inventory planning
- Reduce operational and logistics costs
- Enhance customer satisfaction through timely deliveries
- Enable data-driven decision-making using dashboards

---

## 📊 Problem Statement
A regional retail company faced:
- Increased delivery delays
- Rising inventory holding costs
- Inconsistent supplier lead times

### Key Business Questions:
- Why did delivery delays increase in certain months?
- How can demand be forecasted effectively?
- Which suppliers perform best?
- How to optimize inventory and reduce excess stock?

---

## 🗂️ Data Sources
- **Dataset:** Supply Chain & Logistics Data  
- **Source:** https://excelx.com/practice-data/generators/supply-chain-logistics/  
- **Timeline:** 2022 – 2026  
- **Domain:** Retail Logistics  

---

## 🧩 Data Model (Star Schema)
The data is structured into **Fact and Dimension tables**:

### 🔹 Procurement & Suppliers
- Purchase Orders
- Purchase Order Lines
- Supplier Master
- Raw Materials Master

### 🔹 Inventory & Warehouse
- Warehouse Inventory
- Stock Movements
- Warehouse Master

### 🔹 Transportation
- Shipment Tracking
- Carriers Master

### 🔹 Order Fulfillment
- Customer Sales Orders
- Fulfillment Status

### 🔹 Performance
- Supplier Performance

---

## 🛠️ Tools & Technologies
- **Excel** – Data Cleaning & Transformation  
- **Power Query** – Data Processing  
- **Power BI** – Data Modeling, DAX, Dashboarding  

---

## 🔄 Data Preprocessing
- Removed duplicates and handled missing values
- Standardized formats and cleaned datasets
- Created calculated columns
- Built pivot tables for initial analysis
- Converted data into **Fact & Dimension tables**

---

## 📐 DAX Measures (Key Metrics)

```DAX
-- On-Time %
On-Time % = DIVIDE([On-Time Orders], [Total Orders])

-- On-Time Orders
On-Time Orders =
CALCULATE(
    COUNT(Purchase_Orders[OrderDate]),
    Purchase_Orders[OrderDate] <= Purchase_Orders[ExpectedDeliveryDate]
)

-- Cancelled Orders
Cancelled Orders =
CALCULATE(
    COUNTROWS(Purchase_Orders),
    Purchase_Orders[Delivery Status] = "Cancelled"
)
