# EFS

## Acronym
* EFS - Elastic File System
* IA - Infrequent Access
* CMS - Content Management System
* AMI - Amazon Machine Image
* SG - Security Group
* KMS - Key Management Service
* AZ - Availability Zone
* ENI - Elastic Network Interface

## Intro
* Use case: content management, web serving, data sharing, Wordpress
* Compatible with Linux based AMI (not Windows), POSIX-compliant
* Uses NFSv4.1 protocol
* Uses SG to control access to EFS
* Encryption at rest using KMS
* Can only attach to one VPC, Create one ENI (mount target) per AZ

---

## Performance & Storage Classes
* EFS Scale:
  * 1000s of concurrent NFS clients, 10GB+ /s throughput
  * Grow to Petabyte-scale network file system
* Performance mode (set at EFS creation time)
  * General purpose (default): latency-sensitive use cases (web server, CMS, etc...)
  * Max I/O - higher latency, higher throughput, highly parallel (big data, media processing)
* Throughput Mode
  * Busting Mode: common for filesystems (intensive work, then almost nothing), linked to FS size
  * Provisioned IO Mode: high throughput to storage ratio (if burst is not enough) - expensive
* Storage Tiers (lifecycle management feature - move file after N days)
  * Standard: for frequently accessed file
  * IA: higher cost to retrieve the file, lower price point to store the file
  
---

## On-Premise & VPC Peering
[<img src="https://i.imgur.com/gtbgT62.png">](https://i.imgur.com/gtbgT62.png)
