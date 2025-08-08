Cloud-Based Finance & Business Intelligence System (AWS)
A serverless AWS pipeline that transforms raw retail interaction and sales data into a live, interactive financial dashboard using Amazon Athena, AWS Glue, Amazon S3, and Amazon QuickSight.

📊 Project Overview
This project simulates a Finance & Business Intelligence (BI) system for a retail enterprise. It ingests customer interaction and sales data into AWS, applies automated schema detection, runs SQL-based analytics, and presents the results in a live dashboard.

The architecture is cost-effective, fully serverless, and scalable to real-world enterprise use cases such as:

Retail sales monitoring

Customer behavior analysis

Financial KPI tracking

Real-time operational insights

🧱 Architecture

![Figure 1 – End-to-End AWS Finance & BI Architecture](Figure1.png)  
*This diagram shows the complete serverless AWS pipeline for Finance & Business Intelligence. It includes:*
- *Data ingestion into Amazon S3*
- *Schema detection and cataloging with AWS Glue*
- *SQL querying via Amazon Athena*
- *Visualization with Amazon QuickSight*
- *Optional scaling modules such as Amazon Forecast, API Gateway, and Cognito*



Pipeline Steps
Data Ingestion – Upload raw interaction & sales CSV files to Amazon S3.

ETL & Cataloging – AWS Glue Crawler scans S3, detects schema, and stores metadata in the Glue Data Catalog.

Query Layer – Amazon Athena queries the dataset with SQL, enabling joins, aggregations, and filtering.

Visualization Layer – Amazon QuickSight builds dynamic KPI dashboards, charts, and drill-down reports.

🗃️ Dataset Example
A cleaned dataset (interactions_clean.csv) stored in S3 contains the following structure:

user_id	item_id	event_type	timestamp
User_1	Item_101	VIEW	1744260000
User_1	Item_102	PURCHASE	1744260100
User_2	Item_105	VIEW	1744260200
User_3	Item_106	VIEW	1744260300
User_3	Item_107	PURCHASE	1744260400


![Figure 2 – Athena Table View](Figure 2.png)  
*Athena table view of the `interactions_clean` dataset. This confirms the dataset schema was correctly detected by AWS Glue after ingestion and is ready for SQL queries.*

🔍 Athena SQL Queries
1. Count Events by Type

![Figure 3 – Event Count Query](Figure3.png)  
*Athena SQL query counting events by type (VIEW and PURCHASE). This query is used to calculate customer engagement metrics and identify the distribution of interactions.*
sql
Copy
Edit
SELECT event_type, COUNT(*) AS event_count
FROM interactions_clean_interactions_clean
GROUP BY event_type;
2. Preview First 10 Rows

![Figure 4 – Athena Query Preview](Figure%204.png)  
**Figure 4 – Athena query preview**: This query previews the first 10 rows of the dataset in Athena, validating data quality and confirming schema mapping before deeper analytics.
sql
Copy
Edit
SELECT * FROM interactions_clean_interactions_clean
LIMIT 10;
📈 QuickSight Dashboards
Interactive Pie Chart – Event Types

![Figure 5 – QuickSight Pie Chart](Figure5.png)  
**Figure 5 – QuickSight Pie Chart**: Pie chart in Amazon QuickSight showing VIEW vs PURCHASE distribution. It provides an at-a-glance view of customer behavior patterns, aiding in marketing and sales optimization.

Main Dashboard – Filters & KPIs

![Figure 6 – Main QuickSight Dashboard](Figure6.png)  
**Figure 6 – Main QuickSight Dashboard**: Interactive dashboard with filters (`user_id`, `event_type`) and KPI cards. Displays total views, purchases, and conversion rate for in-depth customer analytics.

![Figure 7 – QuickSight Bar Chart](Figure7.png)  
**Figure 7 – QuickSight Bar Chart**: Bar chart showing event counts over time grouped by event type. Useful for identifying spikes in customer activity and aligning them with campaigns or promotions.
🔁 ETL with AWS Glue

![Figure 8 – AWS Glue Crawler Configuration](Figure8.png)  
**Figure 8 – AWS Glue Crawler Configuration**: AWS Glue Crawler setup screen. Configured to scan the S3 bucket, detect schema changes, and automatically update the Glue Data Catalog so Athena always queries the latest data.

🧠 Advanced Enhancements

![Figure 9 – Future Enhancements Plan](Figure9.png)  
**Figure 9 – Future Enhancements Plan**: Planned AWS enhancements for the BI system. Includes adding Amazon Forecast for sales prediction, integrating Lambda for automation, and extending data ingestion with API Gateway.

✅ Summary Table
Layer	AWS Service
Storage	Amazon S3
ETL	AWS Glue Crawlers
SQL Engine	Amazon Athena
Visualization	Amazon QuickSight
Forecasting (opt)	Amazon Forecast
Real-time ingest	API Gateway + Lambda
User Auth (opt)	Amazon Cognito

🚀 Use Cases
Retail BI dashboards

Customer behavior analytics

Real-time sales monitoring

Cost-optimized analytics for SMEs

🏗️ AWS Services Used
Amazon S3 – Storage layer

AWS Glue – ETL and schema cataloging

Amazon Athena – Serverless SQL queries

Amazon QuickSight – Visualization and dashboards

(Optional) Amazon Forecast, Lambda, API Gateway, Cognito

📁 Repo Structure
bash
Copy
Edit
finance-bi-dashboard/
│
├── Figure1.png   # Architecture Diagram
├── Figure2.png   # Athena Table View
├── Figure3.png   # Event Count Query
├── Figure4.png   # LIMIT Query Preview
├── Figure5.png   # QuickSight Pie Chart
├── Figure6.png   # Main Dashboard
├── Figure7.png   # Bar Chart
├── Figure8.png   # Glue Crawler
├── Figure9.png   # Enhancements Plan
└── README.md


🔗 Author
Joshua Barradas
Cloud AI Researcher | AWS Solutions Builder | Retail + Finance AI
📍 Leeds, UK
📧 barradasjoshua48@gmail.com
🔗 LinkedIn
