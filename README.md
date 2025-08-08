# Cloud-Based Finance & Business Intelligence System (AWS)

A serverless AWS pipeline that transforms raw retail interaction and sales data into a live financial dashboard using Athena, Glue, S3, and QuickSight.

---

## 📊 Project Overview

This project simulates a finance & business intelligence system for a retail company.  
It uses serverless AWS tools to query customer interactions, join them with financial data, and produce real-time dashboards.

---

## 🛠 Architecture

![Architecture Diagram](Figure1.png)

### Pipeline Steps:
- **Data Ingestion:** Raw interaction and sales data uploaded to Amazon S3.  
- **ETL & Cataloging:** AWS Glue crawlers detect schema and create tables.  
- **Query Layer:** Amazon Athena performs SQL joins, filters, and aggregations.  
- **Dashboard Layer:** Amazon QuickSight displays interactive KPI charts.  

---

## 📂 Input Dataset Example

Sample of the cleaned `interactions_clean` dataset stored in S3:

| user_id | item_id  | event_type | timestamp |
|---------|----------|------------|-----------|
| User_1  | Item_101 | VIEW       | 1744260000|
| User_1  | Item_102 | PURCHASE   | 1744260100|
| User_2  | Item_105 | VIEW       | 1744260200|
| User_3  | Item_106 | VIEW       | 1744260300|
| User_3  | Item_107 | PURCHASE   | 1744260400|

![Athena Table View](Figure2.png)

---

## 🔍 Athena SQL Queries

### 1. Count Events by Type
```sql
SELECT event_type, COUNT(*) AS event_count
FROM interactions_clean_interactions_clean
GROUP BY event_type;


2. Preview First 10 Rows
sql
Copy
Edit
SELECT * FROM interactions_clean_interactions_clean
LIMIT 10;


📈 QuickSight Dashboards
Pie Chart – Event Types
Shows distribution of VIEW vs PURCHASE.


Main Dashboard – Filters & KPIs
Includes real-time filters (e.g. user_id, event_type), dynamic KPI cards, and trend charts.


Bar Chart – Events Over Time
X-axis: Event timestamp
Grouped by event_type.


🛠 ETL with AWS Glue
AWS Glue Crawlers automatically scan the S3 bucket, detect schema, and create tables in the Data Catalog.
This enables Athena to immediately query fresh data without manual table setup.



💡 Advanced Enhancements
Simulated optional features using other AWS tools:

Sales forecasting – Amazon Forecast

Real-time ingestion – API Gateway + Lambda

Natural language BI – Amazon QuickSight Q



✅ Summary Table
Layer	AWS Service
Storage	Amazon S3
ETL	AWS Glue Crawlers
SQL Engine	Amazon Athena
Visualization	Amazon QuickSight
Forecasting (opt)	Amazon Forecast
Real-time ingest (opt)	API Gateway + Lambda
User Auth (opt)	Amazon Cognito

🚀 Use Cases
Retail BI dashboards

Customer behavior analytics

Real-time sales monitoring

🗂 Repo Structure
bash
Copy
Edit
finance-bi-dashboard/
│
├── Figure1.png   # Architecture Diagram
├── Figure2.png   # Athena Table View
├── Figure3.png   # SQL Count Query
├── Figure4.png   # LIMIT Query Preview
├── Figure5.png   # QuickSight Pie Chart
├── Figure6.png   # Full Dashboard Screenshot
├── Figure7.png   # Bar Chart of Events
├── Figure8.png   # Glue Crawler Output
├── Figure9.png   # Optional Enhancements
└── README.md
👤 Author
Joshua Barradas
Cloud AI Researcher | AWS Solutions Builder | Retail + Finance AI
📍 Leeds, UK
📧 barradasjoshua48@gmail.com
🔗 LinkedIn

