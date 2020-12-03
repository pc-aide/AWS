# ElasticSearch

## Acronym
* ES - ElasticSearch
* CRUD - Create,Read,Update, & Delete table

## 
* <ins>May be called Amazon ES at the exam</ins>
* Managed version of ElasticSearch (open source project)
* Needs to run on servers (not a serverless offering)
* Use cases:
  * Log Analytics
  * Real Time application monitoring
  * Security Analytics
  * Full Text Search
  * Clickstream Analytics
  * Indexing
  
---

## ElasticSearch + Kibana + Logstash
* ElasticSearch: provide search & indexing capability
  * You must specify instance types, multi-AZ, etc
* Kibana:
  * Provide real-time dashboards on top of the data that sits in ES
  * Alternative to CloudWatch dashboards (more advanced capabilities)
* Logstash:
  * Log ingestion mechanism, use the "Logstash Agent"
  * Alternative to CloudWatch Logs (you decide on retention & granularity)
  
---

## ElasticSearch patterns DynamoDB
[<img src="https://i.imgur.com/wTn3ExG.png">](https://i.imgur.com/wTn3ExG.png)

---

## ES patterns CloudWatch Logs
[<img src="https://i.imgur.com/4MDV7a7.png">](https://i.imgur.com/4MDV7a7.png)
