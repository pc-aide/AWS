# Amazon Athena

## Acronym
* ETL - Extract, Transform, Load
* SQL - Simple Query Language
* ANSI - American National Standards Institute
* EMR - Elastic MapReduce

## Doc
* [Amazon Athena Documentation](https://docs.aws.amazon.com/athena/)
* [What is Amazon Athena?](https://docs.aws.amazon.com/athena/latest/ug/what-is.html)

## Logo
[<img src="https://i.imgur.com/SC62uXN.png">](https://i.imgur.com/SC62uXN.png)

## Intro
* Query Data in S3 using SQL
* Amazon Athena is an interactive **query* service that makes it easy to analyze data
  in Amazon **S3** using standard **SQL**. Athena is serverless, so there is no infrastructure
  to setup or manage, and you pay only for the queries you run. To get started,
  simply point to your data in S3, define the schema, and start querying using standard SQL. 

## AWS Console
1) Select a data set
2) Create a table
3) Query data

[<img src="https://i.imgur.com/TnZnNJW.png">](https://i.imgur.com/TnZnNJW.png)

## What is Athena & key Benefits
* Serverless interactive query tool
* Its not an ETL tool
* Pay per Query ($ = Scanned data volume)

## How Athena Works
* Load data in S3 -> Define the schema -> Query
* Built on Top of Apache Presto
* Works with AWS Glue (Hive like meta store)
* ANSI SQL Compliant
* Popular formats (CSV, JSON, Parquet, AVro, ORC)

[<img src="https://i.imgur.com/f19v6LX.png">](https://i.imgur.com/f19v6LX.png)

## Optimise Cost & Common Workloads

## How ETL Works
[<img src="https://i.imgur.com/hAfdiLu.png">](https://i.imgur.com/hAfdiLu.png)

## Redhisft + EMR + Athena
[<img src="https://i.imgur.com/UJtxPUz.png">](https://i.imgur.com/UJtxPUz.png)

## Pricing
* Pay per query
* No 'data storage' cost, except S3
* $0.05/10 GB or $5.00/1TB of data scanned
