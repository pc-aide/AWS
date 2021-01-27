# Storage Gateway

## Doc
* [Whitepapers-storage-gateway-file-gateway-for-hybrid-architecture](https://d0.awsstatic.com/whitepapers/aws-storage-gateway-file-gateway-for-hybrid-architectures.pdf)

## Acronym
* EBS - Elastic Block Store
* EMR - ElasticMapReduce
* CRR - Cross-Region Replication
* IAM - Identity & Access Management
* iSCSI - Internet Small Computer System Interface
* NFS - Network File System
* SMB - Server Message Block
* VTL - Virtual Tape Library
* WORM - Write Once Read Many

## Intro
* 3x products in 1
  1) File Gateway
     * allows you to transmit file from: on-prem <> AWS 
  2) Volume Gateway
     * have iSCSI block
  3) Tape Gateway
     * if you want ot back up to a tape format
* Bridge between on-premise data & cloud data in S3
* Use cases:
  * disaster recovery, backup & restore, tiered storage

---

## File Gateway
* File Gateway appliance is a VM to bridge between your NFS & S3
* Metadata & directory stucture are preserved
* Configure S3 buckets are accessible using the **NFS & SMB protocol**
* Each File Gateway should have an IAM role to access S3
* Most recently used data is **cached** in the file gateway
* Can be mounted on many servers

### Diagram
[<img src="https://i.imgur.com/N2y99lz.png">](https://i.imgur.com/N2y99lz.png)

---

## File Gateway: Extensions
[<img src="https://i.imgur.com/Y8D5QBu.png">](https://i.imgur.com/Y8D5QBu.png)

---

## File Gateway: Read Only Replicas
[<img src="https://i.imgur.com/DqA992J.png">](https://i.imgur.com/DqA992J.png)

---

## File Gateway: Backup & Lifecycle Policies
[<img src="https://i.imgur.com/Nms0PyJ.png">](https://i.imgur.com/Nms0PyJ.png)

---

## File Architectures: Other possibilities
* S3 Object Versioning
  * Ability to store multiple object versions as they are modified
  * Helpful to restore a file to a previous version
  * Could restore an entire file system to a previous version
  * Must use the "RefreshCache" API on the Gateway to be notified of restore
* S3 Object Lock
  * Enables to have the File Gateway for WORM data
  * If there are file modifications or renames in the file share clients, the file gateway creates a new version of the object without affecting priori versions, & the original locked version will remain unchanged
  
---

## Volume Gateway
* Block storage using **iSCSI protocol** backed by S3
* **Cached volumes**: low latency access to most recent data, full data on S3
* **Stored volumes**: entire dataset is on premise, scheduled backups to S3
* Can create EBS snapshots from the volumes & restore as EBS!
* Up to 32 volumes per gateway
  * Each volume up to 32TB in cached more (1PB per Gateway)
  * Each volume up to 16TB in stored mode (512TB per Gateway)
  
### Diagram
[<img src="https://i.imgur.com/78f0ObQ.png">](https://i.imgur.com/78f0ObQ.png)

---

## Tape Gateway
* Some companies have backup processes using physical tapes
* With Tape Gateway, companies use the same processes but in the cloud
* VTL backed by S3 & Glacier
* Back up data using existing tape-based processes (& iSCSI interface)
* Works with leading backup software vendors
* **You can't access single file within tapes. You need to restore the tape entirely**

### Diagram
[<img src="https://i.imgur.com/JZAbICg.png">](https://i.imgur.com/JZAbICg.png)
