# Athena & Quicksight

## Acronym
* CW - CloudWatch
* ALB - Application Load Balancer
* BI - Business Inteligence
* EMR - Elastic MapReduce
* RDS - Relational Database Service

## Intro
* **Athena**:
  * Serverless SQL queries on top of your data in S3, pay per query, output to S3
  * Supports CSV,JSON, Parquet, ORC
  * Queries are logged in CloudTrail (which can be chained with CW logs
  * Great for spradic queries
  * Ready-to-use queries for VPC Flow Logs, CloudTrail, ALB Access Logs, Cost & Usage reports (billing), etc...
* **Quicksight:**
  * something you visualize your data
  * BI tool for data visualization, creating **dashboards**
  * Integrates with Athena, Redshift, EMR, RDS...
  
---

## Athena
[<img src="https://i.imgur.com/AZxIgzY.png">](https://i.imgur.com/AZxIgzY.png)

---

## Quicksight
[<img src="https://i.imgur.com/4QZsymh.png">](https://i.imgur.com/4QZsymh.png)
