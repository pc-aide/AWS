# Athena

## Doc

## Acronym
* S3 - Simple Storage Service
* VPC - Virtual Private Cloud
* ELB - Elastic Load Balancing

## Intro
* **Serverless** service to perform analytics **directly against S3 files**
* Uses **SQL** language to query the files
* Has a JDBC/ODBC driver
* Charged per query & amount of data scanned
* Supports
    * CSV, json, ORC, Avro, & Parquet (built on Presto)
* Use cases: Business intelligence/analytics/reporting, analyze & query VPC Flow Logs, ELB Logs, CloudTrail trails, etc...
* Exam Tip: Analyze data directly on S3 => use Athena
