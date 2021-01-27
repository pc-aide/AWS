# Storage Classes

## Doc
* [s3 storage-classes](https://aws.amazon.com/s3/storage-classes/)

## Acronym
* AZ - Availability Zone
* IA - Infrequent Access
* SLA - Service Level Agreement
* SSL - Secure Sockets Layer

## Intro
1) S3 Standard - General Purpose
2) S3 Standard-IA
3) S3 One Zone-IA
4) S3 Intelligent Tiering
  * move storage classe, e.g from Glacier -> Glacier deep arhive after 180d
5) Glacier
6) Glacier Deep Archive
7) S3 Reduced Redundancy Storage (deprecated - omitted)

---

## S3 Standard - General Purpose
* High durability (99.999 999 999%) of object across multiple AZs
  * copy on >= 3 AZs
* If you store 10M objects with S3, you can on average expect ot incur a loss of a single object once every 10k years
* 99.99% Availability over a given year
* Sustain 2 concurrent facility failures
* Use Cases: 
  * Bid Data analytics, mobile & gaming applications, content distribution...
  
---

## S3 Standard-IA
* Suitable for data that is less frequently accessed, but requires rapid acces when needed
* High durability (99. 999 999 999%) of objects across multiple AZs
  * copy on >= 3 AZs
* 99.9% Availability
* Low cost compared to S3 standard
* Sutain 2 concurrent facility failures
* Use Cases:
  * As a data store for disater recovery, backups...

---

## S3 One Zone-IA
* Same as IA but data is soted in a sigle AZ
* High durability (99. 999 999 999%) of objects in a single AZ; data lost when AZ is destroyed
* 99.5% Availability
* Low latency & high throughput performance
* Support SSL for data at transit & encryption at rest
* Low cost compared to IA (by 20%)
* Use Cases:
  * Storing secondary backup copies of on-premise data, or storing data you can recreate (e.g.: thumbnails from an image)
  
---

## S3 Intelligent Tiering
* Same low latency & high throughput performance of S3 standard
* Smal monthly monitoring & auo-tiering fee
* Automatically moves objects between two access tiers based on changing access patterns
* Designed for durability of 99.999 999 999% of objects across multiple AZs
* Resilient against events that impact an entire AZ

---

## Glacier
* Low cost object storage meant for archiving/backup
* Data is retained for the longer term (10s of years)
* Alternative to on-premise magnetic tape storage
* Average annual durability is 99.999 999 999%
* Cost per storage per month ($0.004/GB) + retieval cost
* Each item in Glacier is called "**Archive**" (up to 40TB)
* Archives are stored in "**Vaults**"

### Glacier & Glacier Deep Archive
* Glacier - 3 retrieval options:
  1) Expedited (1 to 5 minutes)
  2) Standard (3 to 5 hours)
  3) Bulk (5 to 12 hours)
  * Minimum storage duration of 90 days
* Glacier Deep Archive - flor long term storage - cheaper:
  * Standard (12 hours)
  * Bulk (48 hours)
  * Minimum storage duration of 180 days
  
---

## Table - Comparison
|                                           | S3 Standard                 | S3 Intelligent-<br>Tiering  | S3 Standard-IA              | S3 One Zone-IA              | S3 Glacier                  | S3 Glacier<br>Deep Arcive   |
| ----------------------------------------- | --------------------------- | --------------------------- | --------------------------- | --------------------------- | --------------------------- | --------------------------- |
| Designed for<br>durability                | 99.999 999 999%<br>(11 9's) | 99.999 999 999%<br>(11 9's) | 99.999 999 999%<br>(11 9's) | 99.999 999 999%<br>(11 9's) | 99.999 999 999%<br>(11 9's) | 99.999 999 999%<br>(11 9's) |
| Designed for<br>availability              | 99.99%                      | 99.90%                      | 99.90%                      | 99.50%                      | 99.99%                      | 99.99%                      |
| Availability SLA                          | 99.90%                      | 99%                         | 99%                         | 99%                         | 99.90%                      | 99.90%                      |
| Availability<br>Zones                     | ≥3                          | ≥3                          | ≥3                          | 1                           | ≥3                          | ≥3                          |
| Minimum<br>capacity charge<br>per object  | N/A                         | N/A                         | 128KB                       | 128KB                       | 40KB                        | 40KB                        |
| Minimum<br>storage duration<br>per object | N/A                         | 30 days                     | 30 days                     | 30 days                     | 90 days                     | 180 days                    |
| Retrieval fee                             | N/A                         | N/A                         | per GB retrieved            | per GB retrieved            | per GB retrieved            | per GB retrieved            |



### Table - Ex us-east-2
                                       | S3 Standard    | S3 Intelligent-<br>Tiering | S3 Standard-IA | S3 One Zone-IA | S3 Glacier                                                               | S3 Glacier<br>Deep Arcive                           |
| ------------------------------------- | -------------- | -------------------------- | -------------- | -------------- | ------------------------------------------------------------------------ | --------------------------------------------------- |
| Storage Cost<br>(per GB per<br>month) | $0.02          | $0.0125 -<br>$0.023        | $0.01          | $0.01          | $0.004<br>Minimum 90 days                                                | $0.00099<br>Minimum 180 days                        |
| Retrieval Cost<br>(per 1k requests)   | GET<br>$0.0004 | GET<br>$0.0004             | GET<br>$0.001  | GET<br>$0.001  | GET<br>$0.0004 +<br><br>Expedited - $10<br>Std - $0.05<br>Bulk - $0.025  | GET<br>$0.004 +<br><br>Std - $0.10<br>Bulk - $0.025 |
| Time to retrieve                      | Instantaneous  | Instantaneous              | Instantaneous  | Instantaneous  | Expedited (1 to 5 minutes)<br>Std (3 to 5 hours)<br>Bulk (5 to 12 hours) | Std (12 hours)<br>Bulk (48 hours)                   |
| Monitoring Cost<br>(per 1k objects)   |                | $0.0025                    |                |                |                                                                          |

