Finance & BI Dashboard – AWS vs Azure (Pick n Pay Case Study)
📌 Executive Summary
This project simulates a retail business intelligence pipeline using AWS services (S3, Glue, Athena, QuickSight) to process raw interaction data into actionable dashboards. It compares AWS vs Azure analytics pipelines in cost, flexibility, and ease of use. Simulated for Pick n Pay’s financial and behavioural analytics team.

🧠 Architecture Overview
Figure A.1 – Architecture Diagram
The pipeline begins by uploading customer interaction and financial data into Amazon S3.
AWS Glue crawls and catalogs the data into tables.
Amazon Athena enables SQL queries to aggregate, filter, and join datasets.
Amazon QuickSight visualizes KPIs such as event frequency and purchase patterns.

![Figure A.1](images/Figure\ 1.png)

🛠️ AWS Services Used
Amazon S3 – Stores raw .csv interaction and financial data

AWS Glue – Crawls datasets and builds schema in Glue Data Catalog

Amazon Athena – Runs SQL queries over structured data

Amazon QuickSight – Creates interactive dashboards

IAM – Secures access to Athena, S3, and Glue

CloudWatch – Optional logging for query error/performance monitoring

💡 Key Features
End-to-end BI pipeline built on AWS

Auto-schema detection with Glue Crawlers

SQL-based querying using Athena

QuickSight dashboards with pie/bar/time series

Join queries between event and revenue data

Forecasting and drill-downs

Azure Power BI tested as alternative

✏️ Sample Query Snippet (Athena SQL)
sql
Copy
Edit
SELECT event_type, COUNT(*) AS total_events  
FROM interactions_clean  
GROUP BY event_type;
Aggregates customer events (e.g., VIEW, PURCHASE) from the cleaned dataset using Athena.

📸 Dashboard and Data Pipeline Screenshots
Figure 1 – Sample Table View in Athena
Raw structured table view after Glue ingestion. Shows schema accuracy and SQL-readiness.

![Figure 1](images/Figure\ 1.png)

Figure 2 – AWS Glue Crawler Setup
Crawler configuration for detecting schema from S3 .csv files. Shows ETL automation and Athena integration.

![Figure 2](images/Figure\ 2.png)

Figure 3 – Athena SQL Join Query (Financial + Interaction)
Joins interaction logs with transaction data (e.g., PURCHASE). Enables behaviour + spend analytics.

![Figure 3](images/Figure\ 3.png)

Figure 4 – Aggregating Customer Events by Type (GROUP BY)
SQL-generated summary of user events by type. Helps identify product engagement and usage trends.

![Figure 4](images/Figure\ 4.png)

Figure 5 – Athena LIMIT 10 Query for Validation
Preview query to inspect schema/data structure before downstream reporting.

![Figure 5](images/Figure\ 5.png)

Figure 6 – QuickSight Pie Chart (Event Types)
Interactive pie chart showing user event type distribution (VIEW, PURCHASE).

![Figure 6](images/Figure\ 6.png)

Figure 7 – QuickSight Bar Chart (Event Over Time)
Time-series bar chart showing user events per day. Helps analyse seasonality, campaign peaks.

![Figure 7](images/Figure\ 7.png)

Figure 8 – Forecasting Dashboard (QuickSight ML)
Forecasting + KPI panel with QuickSight ML. Predicts user events and sales trends.

![Figure 8](images/Figure\ 8.png)

Figure 9 – Drill-Down Dashboard (QuickSight Panel View)
Combined pie, bar, and forecast panel. Cross-filtering, interactive exploration. Great for stakeholders.

![Figure 9](images/Figure\ 9.png)

🌱 Future Enhancements
Integrate anomaly detection (e.g., AWS Lookout for Metrics)

Add SageMaker forecasts for demand prediction

Test QuickSight Q for natural language BI

Compare Azure/AWS query latency and tuning

📁 Suggested Repo Structure
bash
Copy
Edit
finance-bi-dashboard/
├── raw_data/         # S3 data samples (.csv)
├── athena_queries/   # SQL queries used for analysis
├── images/           # Screenshots and diagrams (Figures 1–9)
├── quicksight/       # Dashboard JSON exports (optional)
└── README.md         # This file
👤 Contact & Credits
Joshua Barradas
📍 Leeds, UK
📧 barradasjoshua48@gmail.com
🔗 GitHub: @Joshuabarradas234
