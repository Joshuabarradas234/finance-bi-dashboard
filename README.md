Finance & BI Dashboard – AWS vs Azure (Pick n Pay Case Study)
📌 Executive Summary
This project simulates a retail business intelligence pipeline using AWS services (S3, Glue, Athena, QuickSight) to process raw interaction data into actionable dashboards. It compares AWS vs Azure analytics pipelines in cost, flexibility, and ease of use. Simulated for Pick n Pay’s financial and behavioural analytics team.

🧠 Architecture Overview
Figure A.1 – Architecture Diagram
The pipeline begins by uploading customer interaction and financial data into Amazon S3.

AWS Glue crawls and catalogs the data into tables.

Amazon Athena enables SQL queries to aggregate, filter, and join datasets.

Amazon QuickSight visualizes KPIs such as event frequency and purchase patterns.

🛠️ AWS Services Used
• Amazon S3 – Stores raw .csv interaction and financial data
• AWS Glue – Crawls datasets and builds schema in Glue Data Catalog
• Amazon Athena – Runs SQL queries over structured data
• Amazon QuickSight – Creates interactive dashboards
• IAM – Secures access to Athena, S3, and Glue
• CloudWatch – Optional logging for error/performance monitoring

💡 Key Features
• End-to-end BI pipeline built on AWS
• Auto-schema detection with Glue Crawlers
• SQL-based querying using Athena
• QuickSight dashboards with pie/bar/time series
• Join queries between event and revenue data
• Forecasting and visual drill-downs
• Azure Power BI also tested as an alternative

🧪 Sample Query Snippet (Athena SQL)

sql
Copy
Edit
SELECT event_type, COUNT(*) AS total_events  
FROM interactions_clean  
GROUP BY event_type;
This query aggregates customer events (e.g., VIEW, PURCHASE) from the cleaned dataset using Athena.

📸 Dashboard and Data Pipeline Screenshots

Figure 1 – Sample Table View in Athena (Structured Dataset Preview)
Demonstrates a raw yet structured tabular view of user interaction data in Amazon Athena after being ingested and catalogued via AWS Glue. Shows schema accuracy and readiness for SQL querying — foundational for analytics pipelines.

🔍 Figure 2 – AWS Glue Crawler Configuration for Data Cataloging
Displays configuration of the AWS Glue Crawler used to automatically detect schema from raw .csv files stored in S3. Highlights schema inference, automation of ETL setup, and integration with Athena for serverless querying.

🔗 Figure 3 – Athena SQL Join Query (Financial + Interaction Data)
Presents a complex SQL join between interaction logs and transaction records. Demonstrates the ability to correlate user actions (e.g., VIEW, PURCHASE) with financial outcomes, unlocking valuable behavioural insights.

📊 Figure 4 – Aggregating Customer Events by Type (Athena GROUP BY)
Uses SQL aggregation to generate a summary of customer actions segmented by type. Enables rapid identification of event frequency trends, such as product views vs purchases, directly supporting engagement metrics.

✅ Figure 5 – Athena LIMIT Query for Data Validation
Simple preview query to fetch the first 10 rows from the interactions_clean table. Used for data quality validation, schema verification, and confirming ETL correctness before downstream reporting.

🥧 Figure 6 – QuickSight Pie Chart (Event Type Distribution)
An interactive pie chart in Amazon QuickSight that visually breaks down user behaviour by event type (e.g., VIEW vs PURCHASE). Ideal for non-technical stakeholders to grasp user interaction proportions.

📈 Figure 7 – QuickSight Bar Chart of Events by Date (Temporal Patterns)
Visualizes daily user interactions using a time-series bar chart. Supports analysis of peak activity periods, user behaviour seasonality, and temporal performance trends relevant to marketing and ops teams.

🔮 Figure 8 – Forecasting Dashboard (QuickSight ML-Enhanced KPI Panel)
Features advanced forecasting and drill-down capabilities powered by QuickSight’s built-in ML models. Projects future interaction volumes and sales trends, enabling proactive business decision-making.

🧩 Figure 9 – Interactive Drill-Down Dashboard (QuickSight Panel View)
Final compiled QuickSight dashboard showcasing combined pie, bar, and forecast panels. Includes interactivity, filtering, and cross-chart data exploration — suitable for C-level insights and presentations.



🧩 Future Enhancements
• Integrate anomaly detection (e.g., AWS Lookout for Metrics)
• Add SageMaker forecasts for retail demand
• Use QuickSight Q for natural language BI insights
• Compare tuning/latency differences between Azure and AWS pipelines

📁 Suggested Repo Structure

bash
Copy
Edit
finance-bi-dashboard/
├── raw_data/        # S3 data samples (CSV)
├── athena_queries/  # SQL queries used for analysis
├── images/          # Screenshots and architecture diagrams
├── quicksight/      # Dashboard designs or JSON exports
└── README.md        # This file
🙋 Contact & Credits
Joshua Barradas
📍 Leeds, UK
📧 barradasjoshua48@gmail.com
💻 GitHub: @Joshuabarradas234
