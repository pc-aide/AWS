# Demo - Athena

## Acronym
* DB - database

## Doc
* [Working with Query Results, Output Files, and Query History](https://docs.aws.amazon.com/athena/latest/ug/querying.html)
* [How do I analyze my Amazon S3 server access logs using Athena?](https://aws.amazon.com/premiumsupport/knowledge-center/analyze-logs-athena/)
* [Querying Application Load Balancer Logs](https://docs.aws.amazon.com/athena/latest/ug/application-load-balancer-logs.html)

## Intro
* you must have 2x buckets 
* versioning enabled: ex: monitored
* logging Enabled

[<img src="https://i.imgur.com/gPJ9QOi.png">](https://i.imgur.com/gPJ9QOi.png)
[<img src="https://i.imgur.com/IQLG5c3.png">](https://i.imgur.com/IQLG5c3.png)
[<img src="https://i.imgur.com/jfW1PSN.png">](https://i.imgur.com/jfW1PSN.png)

* Warning if you activing just the access-logs, it can take ~5min before new entries in your bucket

### Athena
* Setup a query result location in S3
    * Setups:

[<img src="https://i.imgur.com/0RQZpKo.png">](https://i.imgur.com/0RQZpKo.png)

* Query result location: s3://aws-demo-athena-results/ca-central/


[<img src="https://i.imgur.com/eBKTaLw.png">](https://i.imgur.com/eBKTaLw.png)

* New query 1
````sql
create database s3_access_logs_db;
````

* Error, we need create this Ahena bucket:

[<img src="https://i.imgur.com/3JN8mNu.png">](https://i.imgur.com/3JN8mNu.png)

* fix it & point out result (settings) this bukcket
* try agin your query
````bash
aws s3 mb s3://demo-01-athena
````
[<img src="https://i.imgur.com/mP0dARV.png">](https://i.imgur.com/mP0dARV.png)
[<img src="https://i.imgur.com/F6Ayupl.png">](https://i.imgur.com/F6Ayupl.png)
[<img src="https://i.imgur.com/a2CXpG3.png">](https://i.imgur.com/a2CXpG3.png)
[<img src="https://i.imgur.com/xoqZHH3.png">](https://i.imgur.com/xoqZHH3.png)

* Database: s3_access_logs_db
* new query:
````sql
CREATE EXTERNAL TABLE IF NOT EXISTS s3_access_logs_db.mybucket_logs(
         BucketOwner STRING,
         Bucket STRING,
         RequestDateTime STRING,
         RemoteIP STRING,
         Requester STRING,
         RequestID STRING,
         Operation STRING,
         Key STRING,
         RequestURI_operation STRING,
         RequestURI_key STRING,
         RequestURI_httpProtoversion STRING,
         HTTPstatus STRING,
         ErrorCode STRING,
         BytesSent BIGINT,
         ObjectSize BIGINT,
         TotalTime STRING,
         TurnAroundTime STRING,
         Referrer STRING,
         UserAgent STRING,
         VersionId STRING,
         HostId STRING,
         SigV STRING,
         CipherSuite STRING,
         AuthType STRING,
         EndPoint STRING,
         TLSVersion STRING
) 
ROW FORMAT SERDE 'org.apache.hadoop.hive.serde2.RegexSerDe'
WITH SERDEPROPERTIES (
         'serialization.format' = '1', 'input.regex' = '([^ ]*) ([^ ]*) \\[(.*?)\\] ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) \\\"([^ ]*) ([^ ]*) (- |[^ ]*)\\\" (-|[0-9]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) (\"[^\"]*\") ([^ ]*)(?: ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*) ([^ ]*))?.*$' )
LOCATION 's3://awsexamplebucket-logs/prefix'
````

* & change location for our location (access-logs bucket):
* run query:

[<img src="https://i.imgur.com/Vt3Xp8z.png">](https://i.imgur.com/Vt3Xp8z.png)
[<img src="https://i.imgur.com/Clwfzxc.png">](https://i.imgur.com/Clwfzxc.png)

* New table:

[<img src="https://i.imgur.com/KUonGIi.png">](https://i.imgur.com/KUonGIi.png)

* Preview table:

[<img src="https://i.imgur.com/XjoJJY8.png">](https://i.imgur.com/XjoJJY8.png)
[<img src="https://i.imgur.com/sY0v44I.png">](https://i.imgur.com/sY0v44I.png)

* New query:
````sql
SELECT requesturi_operation, httpstatus, count(*) FROM "s3_access_logs_db"."mybucket_logs"
GROUP BY requesturi_operation, httpstatus;
````
[<img src="https://i.imgur.com/BuuIlML.png">](https://i.imgur.com/BuuIlML.png)

* New sql
````sql
SELECT count(*) FROM "s3_access_logs_db"."mybucket_logs";
````
[<img src="https://i.imgur.com/nFOilM7.png">](https://i.imgur.com/nFOilM7.png)

* New sql
````sql
SELECT * FROM "s3_access_logs_db"."mybucket_logs"
WHERE httpstatus='403';
````
[<img src="https://i.imgur.com/xWI37hS.png">](https://i.imgur.com/xWI37hS.png)
