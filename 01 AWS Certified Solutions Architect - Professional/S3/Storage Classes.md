# Storage Classes

## Acronym
* AZ - Availability Zone
* IA - Infrequent Access
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
