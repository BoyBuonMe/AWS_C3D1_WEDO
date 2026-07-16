---
title: "Week 10 Worklog"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.10. </b> "
---



### Week 10 Objectives:
* Identify cost anomalies and forecast future spend using AWS Cost Explorer and Anomaly Detection.
* Build an ETL pipeline that transforms raw data before cataloging and querying it in a Data Lake.
* Configure log-based metric filters and cross-account dashboards for infrastructure monitoring with Amazon CloudWatch.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| :--- | :--- | :--- | :--- | :--- |
| 2-3 | **Cost Visualization:** Enable Cost Anomaly Detection to catch unexpected spending spikes, build a monthly cost forecast using Cost Explorer's forecasting feature, and set up a Cost and Usage Report (CUR) delivered to S3 for deeper analysis. | 22/06/2026 | 23/06/2026 | https://000034.awsstudygroup.com/1-introduction/ |
| 4 | **Data Lake on AWS:** Write an AWS Glue ETL job to clean and transform raw data before cataloging, partition data in S3 to speed up Athena query performance, and build a QuickSight dashboard with calculated fields for a music analytics project. | 24/06/2026 | 24/06/2026 | https://000035.awsstudygroup.com/1-introduction/ |
| 6 | **Amazon CloudWatch:** Create metric filters to extract custom metrics from raw log data, build a cross-account Dashboard aggregating metrics from multiple AWS accounts, and configure Container Insights alerts for ECS task failures. | 26/06/2026 | 26/06/2026 | https://000036.awsstudygroup.com/1-introduction/ |

### Week 10 Achievements:
* **Cost Management:** Enabled Cost Anomaly Detection to catch unexpected spending spikes early, and built a Cost and Usage Report pipeline in S3 to support deeper, more granular cost analysis than Cost Explorer alone provides.
* **Big Data Architecture (Data Lake):** Wrote a Glue ETL job to clean and transform raw data before cataloging, and partitioned data in S3 to significantly improve Athena query speed and reduce query costs for the analytics dashboard.
* **System Monitoring (CloudWatch):** Created custom metric filters to extract meaningful signals from raw log data, and built a cross-account Dashboard giving a single, aggregated view of infrastructure health across multiple AWS accounts.