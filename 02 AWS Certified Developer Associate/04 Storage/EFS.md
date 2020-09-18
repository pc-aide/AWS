# EFS

## Acronym
* EFS - Elastic File System
* NFS - Network File System
* AZ - Availability Zone
* HA - High Avalable
* SG - Security Group (managed connection IN/OUT)
* KMS - Key Management Service
* CMS - Content Management System

## Doc
* [What Is Amazon Elastic File System?](https://docs.aws.amazon.com/efs/latest/ug/whatisefs.html)
* [Mounting EFS file systems](https://docs.aws.amazon.com/efs/latest/ug/mounting-fs.html#mounting-fs-mount-cmd)
* [Walkthrough: Create and Mount a File System On-Premises with AWS Direct Connect and VPN](https://docs.aws.amazon.com/efs/latest/ug/efs-onpremises.html)

## Introduction
* Mnaged NFS that can be mounted on many EC2
* EFS works with EC2 instances in multi-AZ
* HA, scalable, expensive (3x gp2), pay per use
* Your EFS attached a SG
* Use cases: content management, web serving, data sharing, Wordpress
* Uses NFSv4.1 protocol
* Uses SG to control access to EFS
* Compatible with Linux based AMI (not Windows)
* Encryption at rest using KMS
* POSIX file system (~Linux) that has a standard file API
* File system scales automatically, per-per-use, no capacity planning!

### Topology
[<img src="https://i.imgur.com/XH08jaf.png">](https://i.imgur.com/XH08jaf.png)

---

## Performance & Storage Classes
* EFS Scale
    * 1000s of current NFS clients, 10GB+ /s throughput
    * Gorw to Petabyte-scale network file system, automatically
* Performance mode (set at EFS creation time)
    * General purpose (default): latency-sensitive use cases (web server, CMS, etc...)
    * Max I/O - higher latency, throughput, highly parallel (big data, media processing)
* Storage Tiers (lifecycle managment feature - move file after N days)
    * Standard: for frequently accessed files
    * Infrequent access (EFS-IA): cost to retrieve files, lower price to store
