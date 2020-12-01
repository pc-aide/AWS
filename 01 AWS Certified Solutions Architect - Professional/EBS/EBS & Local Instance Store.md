# EBS & Local Instance Store

## Acronym
* EBS - Elastic Block Store
* AMI - Amazon Machine Image
* DR - Disaster Recovery
* AZ - Availability Zone
* HDD- Hard Disk Drive
* IA - Infrequent Access

## EBS
* **Network** drive you attach to <ins>ONE</ins> instance only
* Linked to a specific AZ (transfer: snapshot => restore)
* Volumes can be resized
* Make sure you choose an instance type that is EBS optimized to enjoy maximum throughput

### Diagram
[<img src="https://i.imgur.com/yXJ7Vr3.png">](https://i.imgur.com/yXJ7Vr3.png)

---

## Volume Types
1) gp2: General Purpose volumes (cheap)
  * 3 IOPS/GiB, minimum 100 IOPS, bust to 3k IOPS, max 16k IOPS
  * 1GB @ 16TB, +1TB =+3k IOPS
  * 5.5TB so, you have maximum IOPS = 16k IOPS
2) io1: Provisioned IOPS (expensive)
  * Min 100 IOPS, Max 64k IOPS (Nitro) or 32k (other)
  * 4GB @ 16TB. Size of volume & IOPS are independent
3) st1: Throughput Optimized HDD
  * 500GB @ 16TB, 500 MiB/s throughput
  * Good for **big data** workloads
4) sc1: Cold HDD, IA data
  * 250GiB @ 16TB, 250 MiB/s throuput
  
---

## RAID Configuration
* RAID 0 or stretch
  * RAID 0 faster than RAID 1, but if one disk fail, so all data fail
* RAID 1 or mirror

### Diagram
[<img src="https://i.imgur.com/aZWeM79.png">](https://i.imgur.com/aZWeM79.png)

---

## Snapshots
* Incremental - only backup changed blocks
* EBS backups use IO & you shouldn't run them while your application is handling a lot of traffic
* Snapshots will be stored in S3 (but you won't directly see them)
* Not necessary to detach volume to do snapshot, but recommended
* Can copy snapshots across region (for DR)
* Can make AMI from Snapshot
* EBS volumes restored by snapshots need to be pre-warmed using fio or dd command to read the entire volume)
* **Snapshots can be automated using Amazon Data Lifecycle Manager**

---

## Local EC2 Instance Store
* Physical disk attached to the physical server where your EC2 is
* Very High IOPS (because physical)
* Disks up to 7.5TB (can change over time), stripped to reach 30TB (can change over time...)
* Block storage (just like EBS)
* Can't be increased in size
* Risk of data loss if hardware fails
* For IOPS about >= 70k 

| Instance Size | 100% Random Read IOPS | Write IOPS  |
|---------------|-----------------------|-------------|
| i3.large*     | 100.125k              | 35k         |
| i3.xlarge*    | 206.25k               | 70k         |
| i3.2xlarge    | 412k                  | 180k        |
| i3.4xlarge    | 825k                  | 360k        |
| i3.8xlarge    | 1.65 million          | 720k        |
| i3.16xlarge   | 3.3 million           | 1.4 million |
| i3en.large*   | 3.3 million           | 1.4 million |
| i3en.large*   | 42.5k                 | 32.5k       |
| i3en.xlarge*  | 85k                   | 65k         |
| i3en.2xlarge* | 170k                  | 130k        |
| i3en.3xlarge  | 250k                  | 200k        |
| i3en.6xlarge  | 500k                  | 400k        |
| i3en.12xlarge | 1 million             | 800k        |
| i3en.24xlarge | 2 million             | 1.6 million |
| i3en.metal    | 2 million             | 1.6 million |


---

## EBS vs Instance Store
* Some instance don't come with Root EBS volumes
* Instead, they come with "Instance Store" (= ephemeral storage)
* Instance store is physically attached to the machine (EBS is a network drive)
* Pros:
  * Better I/O performance (EBS gp2 has an max IOPS of 16k, io1 of 64k)
  * Good for buffer/cache/scratch data/temporary content
  * Data survices reboots
* Cons:
  * On stop or termination, the instance store is lost
  * You can't resize the instance store
  * Backups must be operated by the user
