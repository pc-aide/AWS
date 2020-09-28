# S3 Storage Tiers + Glacier

## Acronym
* Std - Standard
* IA - Infrequent-Access
* GP - General Purpose
* AZ - Availability Zone
* DR - Disaster Recovery

## Doc
* [Amazon S3 Storage Classes](https://aws.amazon.com/s3/storage-classes/)

## Intro
1) S3 Std - General Purpose
2) S3 Std-IA
3) S3 One Zone-IA
4) S3 Intelligent Tiering
5) Glacier
6) Galcier Deep Archive
7) S3 Reduced Redundancy Storage (deprecated - omitted)

### Diagram
[<img src="https://i.imgur.com/XgaJHoi.png">](https://i.imgur.com/XgaJHoi.png)

---

## 1) S3 Std - GP
* High dirability: 99.999 999 999% of objects across multiple AZs
* If you store 10 millions objects with S3, you can on average expect to incur a loss of a single object once every 10k years
* 99.99% Availability over a given year
* Sustain 2 concurrent facility failures
* Use Cases: **Big Data analytics, mobile & gaming** applications, content distribution...

---

## 2) S3 Std-IA
* Suitable for data that is less frequently accessed, but requires rapid access when needed
* High durability: 99.999 999 999% of objects across multiple AZs
* 99.9% Availability
* Low cost compared to S3 Std
* Sustain 2 concurrent facility failures
* Use Case: As data store for **DR, backups**...

---

## 3) S3 One zone-IA
* Same as IA but data is sotred in **a single AZ**
* High durability: 99.999 999 999% of objects in **a single AZ**; data lost when AZ is destroyed
* 99.5% Availability
* Low latency & high throughput performance
* Supports **SSL** for data at transit & encryption at rest
* Low cost compared to IA (by 20%)
* Use Cases: Storing **secondary backup** copies of non-premise data, or storing data you can recreate
    * E.x: we can recreate **thumbnails** from an image
    
---

## 4) S3 Intellignet Tiering
* Same low latency & high throughput performance of S3 Std
* Small monthly monitoring & auto-tiering fee
* Automatically moves objects between tow access tiers based on changing access patterns
* Designed for durability of 99.999 999 999% of objects across multiple AZs
* Resilient against events that impact an entire AZ 

---

## 5) Glacier
* Low cost object storage meant for archving / backup
* Data is retained for the longer term (10s of years)
* Alternative on-premise **magnetic tape** storage
* Average annual durability is 99.999 999 999%
* Cost per storage per month ($0.004/GB) + retrieval cost
* Each item in Glacier is called "**Archive**" (up to 40TB)
* Archives are stored in "**Vaults**"

---

## 6) Glacier & Glacier Deep Archive
* Glacier - 3 retrieval options
    * Expedied (1 to 5 minutes)
    * Std (3 to 5 hours)
    * Bulk (5 to 12 hours)
    * Minimum storage duration of 90 days
* Glacier Deep Archive - for long term storage - cheaper
    * Std (12 hours)
    * Bulk (48 hours)
    * Minimum storage duration of 180 days
    
---

## S3 Storage Classess Comparison
Stats:

[<img src="https://i.imgur.com/wdHIKso.png">](https://i.imgur.com/wdHIKso.png)

* Price:

[<img src="https://i.imgur.com/MXQ9nix.png">](https://i.imgur.com/MXQ9nix.png)

---

## Demo
````bash
aws s3 mb s3://demo-01-storage-class
# upload 
aws s3 cp cat.jpg s3://demo-01-storage-class
aws s3api list-objects --bucket demo-01-storage-class | grep 'Key\|StorageClass'
````
[<img src="https://i.imgur.com/ZJTzTTL.png">](https://i.imgur.com/ZJTzTTL.png)
