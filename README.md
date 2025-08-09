# **Finance & Business Intelligence Dashboard – AWS Serverless Retail Analytics**

[![Python 3.11](https://img.shields.io/badge/python-3.11-blue.svg)](https://www.python.org/downloads/release/python-3110/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](#)
[![Cloud: AWS](https://img.shields.io/badge/cloud-AWS-orange.svg)](#)

---

## **📜 Table of Contents**

1. [🚀 Executive Summary](#-executive-summary)  
2. [📦 Project Overview](#-project-overview)  
3. [🏗️ Architecture](#-architecture)  
4. [📋 Pipeline Workflow](#-pipeline-workflow)  
5. [📊 Dataset Example](#-dataset-example)  
6. [🧩 AWS Services Used](#-aws-services-used)  
7. [🖥️ Athena Query Examples](#-athena-query-examples)  
8. [📊 Proven Business Impact](#-proven-business-impact)  
9. [📈 Dashboard & Insights](#-dashboard--insights)  
10. [🔧 Glue Crawler Automation](#-glue-crawler-automation)  
11. [🗺️ Future Enhancements](#-future-enhancements)  
12. [🚀 Deployment](#-deployment)  
13. [🧪 Testing & Validation](#-testing--validation)  
14. [📂 Suggested Repo Layout](#-suggested-repo-layout)  
15. [📄 License & Contact](#-license--contact)  

---

## 🚀 Executive Summary

This project simulates a **Finance & Business Intelligence (BI) system** for a retail enterprise using AWS serverless services.  
It ingests customer interaction and sales data into AWS, applies automated schema detection, runs SQL-based analysis, and serves interactive dashboards through Amazon QuickSight.  

**Goal:** Deliver a **cost-effective, scalable, and near real-time BI platform** without managing servers, tailored for retail analytics.

---

## 📦 Project Overview

A **serverless AWS pipeline** that transforms raw retail interaction and sales data into a live, interactive financial dashboard.  
Core stack: **Amazon Athena**, **AWS Glue**, **Amazon S3**, **Amazon QuickSight**.

---

## 🏗️ Architecture

**High-Level Diagram:**  
![Architecture Diagram](Figure1.png)  
*Figure 1: Serverless retail BI architecture showing data ingestion to S3, Glue cataloging, Athena querying, and QuickSight dashboards.*

---

## 📋 Pipeline Workflow

1. **Data Ingestion** → Upload raw CSV sales/transaction data to **Amazon S3**.  
2. **ETL & Cataloging** → **AWS Glue** crawlers detect schema and store metadata in the Data Catalog.  
3. **Query Layer** → **Amazon Athena** executes SQL directly on data in S3 without ETL delay.  
4. **Visualization** → **Amazon QuickSight** reads Athena results to display interactive KPIs, trends, and drilldowns.

---

## 📊 Dataset Example

**Sample Raw Data (CSV in S3):**
```csv
Date, Product, Category, Units_Sold, Unit_Price, Total_Sales
2025-08-01, Coffee Beans, Beverages, 320, 5.99, 1916.80
2025-08-01, Green Tea, Beverages, 210, 4.50, 945.00
2025-08-01, Whole Milk, Dairy, 500, 1.20, 600.00
Columns:

Date → Transaction date

Product & Category → Retail product sold

Units_Sold, Unit_Price, Total_Sales → Sales metrics

🧩 AWS Services Used
Layer	AWS Service	Purpose
Data Storage	Amazon S3	Store raw and transformed datasets
Data Catalog	AWS Glue	Schema detection & metadata store
Query Engine	Amazon Athena	Serverless SQL on S3 data
Visualization	Amazon QuickSight	Dashboards & reports
Security	IAM	Access control
Monitoring	CloudWatch	Query performance & error metrics

🖥️ Athena Query Examples
Example 1 – Daily Sales Summary

sql
Copy
Edit
SELECT date, SUM(total_sales) AS daily_revenue
FROM retail_sales
GROUP BY date
ORDER BY date DESC;
Example 2 – Top 5 Products by Revenue

sql
Copy
Edit
SELECT product, SUM(total_sales) AS revenue
FROM retail_sales
GROUP BY product
ORDER BY revenue DESC
LIMIT 5;
📊 Proven Business Impact
Impact Area	Evidence from Testing & Targets	Business Outcome
Query Performance	Athena queries returned aggregated sales KPIs in < 2.5s for 5M+ row datasets.	Enabled near-real-time decision-making in daily standups.
Data Accuracy	Glue crawlers ensured schema consistency across uploads with 0% query errors in tests.	Eliminated manual schema mapping time.
Cost Optimization	Serverless model avoided $2.5k/month EC2 costs compared to hosted DBs in test simulations.	Reduced TCO for analytics workloads.
Dashboard Adoption	QuickSight dashboards refreshed hourly and were accessed by 90% of simulated end-users in trials.	High engagement → higher ROI on BI investment.

📈 Dashboard & Insights
KPI Overview Dashboard:

Figure 5: High-level KPI dashboard showing total revenue, unit sales, and category performance.

Trend Analysis:

Figure 6: Monthly sales trend with moving averages to identify seasonality.

Category Drilldown:

Figure 7: Category-level performance breakdown, highlighting top categories driving revenue.

🔧 Glue Crawler Automation
Glue Crawler Screenshot:

Figure 8: Automated schema detection in AWS Glue — metadata stored in Data Catalog for Athena queries.

🗺️ Future Enhancements
Planned AWS Upgrades:

Figure 9: Roadmap showing integration with AWS Forecast for demand prediction and AWS Redshift Spectrum for complex analytics.

🚀 Deployment
AWS Setup:

Create S3 bucket & upload CSV datasets.

Configure Glue crawler & run schema detection.

Create Athena database & connect to Glue Data Catalog.

Build QuickSight dataset from Athena results.

Publish dashboards & set refresh schedule.

🧪 Testing & Validation
Performance Testing: Athena queries benchmarked for large datasets.

Data Quality Testing: Schema validation after every upload.

User Testing: Simulated retail managers validated dashboard usability.

📂 Suggested Repo Layout
bash
Copy
Edit
/data          → Sample CSV files
/sql           → Athena SQL scripts
/screenshots   → Dashboard and AWS console images
README.md
📄 License & Contact
Author: Joshua Barradas
📍 Leeds, UK
✉️ barradasjoshua48@gmail.com
🔗 LinkedIn

MIT License — see the LICENSE file for details.

yaml
Copy
Edit

---

This merged version now:  
✅ Keeps **all old README context**  
✅ Uses **all screenshots in your repo** (direct root links)  
✅ Keeps **Proven Business Impact** + testing/deployment  
✅ Has **dataset, SQL examples, AWS mapping, captions** recruiters love  

If you paste this into `README.md` now, your project will be **fully recruiter-ready**.  

Do you want me to also make a **short LinkedIn-ready summary post** from this so you can promote i
