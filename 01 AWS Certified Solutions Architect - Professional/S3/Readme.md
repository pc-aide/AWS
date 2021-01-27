# S3

## Acronym
* CRR - Cross Region Replication
* DLQ - Dead Letter Queue
* SRR - Same Region Replication

## Doc
* [S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/)
* [Logging S3 API calls using CloudTrail](https://docs.aws.amazon.com/AmazonS3/latest/dev/cloudtrail-logging.html)
* [S3 Select and Glacier Select – Retrieving Subsets of Objects](https://aws.amazon.com/blogs/aws/s3-glacier-select/)

## Intro
* Object storage, serverless, unlimited storage, pay-as-you-go
* Good to store static content (image, video files)
* Access objects by key, no indexing facility
* Not a filesystem, can't be mounted natively on EC2
* Anti patterns:
  * Lots of small files
  * POSIX file system (use EFS instead), file locks
  * Search features, queries, rapidly changing data
  * Website with dynamic content
  
---

## Storage Classes Comparison
|                                       | S3 standard                   | S3 Intelligent-Tiering        | S3 Standard-IA                | S3 One Zone-IA                | S3 Glacier                    | S3 Glacier<br>Deep Archive    |
| ------------------------------------- | ----------------------------- | ----------------------------- | ----------------------------- | ----------------------------- | ----------------------------- | ----------------------------- |
| Designed for<br>durability            | 99\. 999 999 999%<br>(11 9's) | 99\. 999 999 999%<br>(11 9's) | 99\. 999 999 999%<br>(11 9's) | 99\. 999 999 999%<br>(11 9's) | 99\. 999 999 999%<br>(11 9's) | 99\. 999 999 999%<br>(11 9's) |
| Designed for<br>availability          | 99.99%                        | 99.90%                        | 99.90%                        | 99.50%                        | 99.99%                        | 99.99%                        |
| Availability SLA                      | 99.90%                        | 99%                           | 99%                           | 99%                           | 99.90%                        | 99.90%                        |
| AZs                                   | ≥3                            | ≥3                            | ≥3                            | 1                             | ≥3                            | ≥3                            |
| Minimum<br>storage duration<br>charge | N/A                           | 30 days                       | 30 days                       | 30 days                       | 90 days                       | 180 days                      |
| Retrieval fee                         | N/A                           | N/A                           | per GB retrieved              | per GB retrieved              | per GB retrieved              | per GB retrieved              |


* You can transition objects between tiers (or delete) using S3 Lifecycle Policies

---

## Replication
* CRR
* SRR
* Combine with Lifecycle Policies
* Helpful to reduce latency
* Helpful for disaster recovery
* Helpful for security
* S3 bucket vesioning must be enabled

### Diagram
[<img src="https://i.imgur.com/cDsQeYN.png">](https://i.imgur.com/cDsQeYN.png)

---

## Events Notifications
* S3:ObjectCreated, S3:ObjectREmoved, S3:ObjectREstore,S3:Replication...
* Object name filtering possible (*.jpg)
* <ins>Use case:</ins> generate thumbnails of images uploaded to S3
* S3 event notifications typically deliver events in seconds but can sometimes take a minutes or longer
* If two writes are made to a single non-versioned object at the same time, it's possible that only a single event notification weill be sent
* If you want to ensure that an event notification is sent for every successful write, you can enable versioning on your bucket

### Diagram
[<img src="https://i.imgur.com/URzAx3q.png">](https://i.imgur.com/URzAx3q.png)

---

## CloudWatch Events
* By default, CloudTrail records S3 bucket-level API calls
* CloudTrail logs for **object-level** S3 actions can be enabled
* This helps us generate events for object-level API (GetObject, PutObject,DeleteObject,**PutObjectAcl**, etc...)

### Diagram
[<img src="https://i.imgur.com/QSBzPnz.png">](https://i.imgur.com/QSBzPnz.png)

---

## Baseline Performance
* S3 automatically scales to high request rates, latency 100-200 ms
* Your application can achieve at least **3.5k PUT/COPY/POST/DELETE** & **5.5k GET/HEAD request per second** per prefix in a bucket
* There are no limits to the number of prefixes in a bucket
* <ins>Example (object path => prefix):</ins>
  * bucket/folder1/sub1/file => /folder1/sub1/
  * bucket/folder1/sub2/file => /folder1/sub2/
  * bucket/1/file => /1/
  * bucket/2/file => /2/
* If you spread reads across all four prefixes evenly, you can achieve 22k requests per second for GET & HEAD

---

## Performance
* Multi-Part upload:
  * recommended for files > 100MB
  * must use for files > 5GB
  * Can help parallelize uploads (speed up transfers)
* S3 **Transfer Acceleration (upload only**)
  * Increase tranfer speed by transferring file to an AWS edge location which will forward the data to the S3 bucket in the target region
* Compatible with multi-part upload
  
### Diagram
[<img src="https://i.imgur.com/ifnd5td.png">](https://i.imgur.com/ifnd5td.png)

---

## Performance - S3 Byte-Range Fetches
* Parallelize GETs by requesting specific byte ranges
* Better resilience in case of failures

### Diagram
[<img src="https://i.imgur.com/sMTUKcF.png">](https://i.imgur.com/sMTUKcF.png)

---

## S3 Select & Glacier Select
* Retrieve less data using SQL by performing **server side filtering**
* Can filter by rows & columns (simple SQL statements)
* Less network transfer, less CPU cost client-side

### Diagram
[<img src="https://i.imgur.com/UmsMPJT.png">](https://i.imgur.com/UmsMPJT.png)

[<img src="https://i.imgur.com/dclqkkH.png">](https://i.imgur.com/dclqkkH.png)

---

## Limits
* Soft limits (we can contact Amazon to raise the quota)
  * 100 bucket / account
* 5 TB max / object

---

## Cost Savings
* **S3 Select & Glacier Select**: save in network & CPU cost
* **S3 Lifecyle Rules**: transition objects between tiers
* **Compress Objects** to save space
* **S3 Requester Pays**
  * In general, bucket owners pay for all Amazon S3 storage & data transfer costs associated with their bucket
  * With Requester Pays buckets, the requester instead of the bucket owner pays the cost of the request & the data download from the bucket
  * The bucket owner always pays the cost of storing data
  * Helpful when you want ot share large datasets with other accounts
    * To enable this feature, you need to add in the policy bucket
  * ** If an IAM role is assumed, the owner account of that role pays for the request**
    
