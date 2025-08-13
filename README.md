# POLYSCAN – Election Contributions Analytics
💡 Turning U.S. political donation data into insights, trends, and transparency.

##📌 Overview
Ever wondered who’s funding U.S. elections?
POLYSCAN is an end-to-end big data analytics platform that processes the publicly available OpenFEC datasets to uncover trends, anomalies, and donor behavior in political contributions.

Using a scalable AWS-based data pipeline and interactive dashboards, the system enables:

🗳 Political analysts to study campaign finance trends

🕵️ Regulators & journalists to detect suspicious donations

📊 The public to explore donation patterns easily

## 🗂 Datasets Used
📂 Primary Sources:

🗃️ Individual Contributions Dataset — All donations made by individuals.

🗃️ Committee Master — Committees receiving contributions.

🗃️ Candidate Master — Candidate details, elections, and party affiliation.

##📌 Data Relationship:

nginx
Copy
Edit
Individuals → Committees → Candidates → Elections
🎯 Project Objectives
 Clean & structure raw OpenFEC datasets (~40 GB) for analysis.

 Identify key features — donation amounts, donor demographics, transaction types.

 Detect unusual or suspicious donations using rule-based validation checks.

 Create interactive dashboards to visualize donation patterns and anomalies.

## 🏛 Architecture


Our system follows a Medallion Architecture with Bronze, Silver, and Gold layers:

Bronze Layer – Stores raw OpenFEC data for reference.

Silver Layer – Data cleaning, standardization, and enrichment (AWS Glue + Amazon EMR).

Gold Layer – Optimized, query-ready data for analytics (Amazon Athena + Power BI).

## Services Used:

AWS Glue – ETL & schema discovery

AWS Glue Crawler – Automated schema inference

Amazon EMR (Spark) – Large-scale distributed data processing

Amazon Athena – Serverless SQL querying on S3

Power BI – Interactive dashboard & visualization

(Insert your architecture diagram image here)

## 🔍 Key Transformations
Split transaction_amt into:

CONTRIBUTION_AMT (positive donations)

REFUND_AMT (negative refunds)

Standardized party affiliation values (replaced (I) or . with "UNDEFINED")

Cleaned missing values & removed duplicates

Standardized date formats & donor details

Filtered relevant election years (2013–2025)

## 📊 KPIs & Metrics
KPI	Description
💵 Total Contributions	Sum of all donations
📈 Average Donation Size	Mean contribution amount
🔄 Donor Retention Rate	% of repeat donors
🗺 Regional Contribution	Donations by state/city
📌 Refund Rate	% of donations refunded
🎯 Earmarked Contribution Ratio	Share of donations for specific purposes

## 📌 Expected Outcomes
📂 Clean, structured dataset ready for analysis

🖥 Interactive dashboard for public or organizational use

📊 Trends & patterns in political donations

🚨 Detection of suspicious contributions

🌍 Insights into who is donating — location, occupation, demographics

## 💡 Use Cases
👨‍💼 Campaign Managers – Optimize fundraising & track competition
🏛 Regulatory Bodies (FEC) – Enhance compliance & fraud detection
🕵️ Investigative Journalists – Uncover influence networks
📢 Public & Advocacy Groups – Promote transparency & reform

## ✨ Impact
POLYSCAN transforms complex, large-scale political donation data into clear, actionable insights.
It empowers citizens, analysts, and regulators to track money in politics, ensuring fairness, transparency, and trust in the electoral process.

