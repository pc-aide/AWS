# Storage Options

## Acronym
* EBS - Elastic Block Store
* EFS - Elastic File System
* FSx - File Server
* IA - Infrequent Access
* HA - High Availability
* gp - general purpose <version>

## Intro
1) EBS
2) EFS
3) Instance Store

---

## EBS
1) SSD
  * gp2 (default
  * Provisioned IOPS: io1 or io2
2) HDD
  * Trhoughput optimized
    * frequently access
  * Cold
    * infrequently acces (lowest cost)
      

### Diagram
* 2TB for 12hrs
  * Provisoned IOPS
    * ~$5.25 for 1k IOPS provisioned
  * Throughput Optimized
    * $3.33
  * gp
    * $1.5
  * Cold HDD
    * $0.83 cents
    
[<img src="https://i.imgur.com/VvAXSmP.png">](https://i.imgur.com/VvAXSmP.png)

---

## EFS
* Managed NFS file system
* HA & scalable
* Automatically grows & shrinks
  * Only pay for what you use
  * EBS - pay for entire allocated volume
* Multiple instances can access file system
* EFS for only Linux
* **FSx** for use with **Windows**
  * SMS, Active Direcotry
  
---

## EFS Options
### Access
* Standard storage
  * Active files
  * Pay for amount of storage use each month
* IA
  * Less active files
  * Lower monthly cost + access fee to read/write
* Lifecycle management
  * Automatically move files to IA if not accessed for period of time
  * e.g an app that heavily used new files for 7 days, then the files are only accessed occasionally if someone searches for them, you could set your time period to 7 days
  
### Perfomance
1) Busting
2) Provisoned
  * if you need more throughput than is allowed by busting
3) General purpose
4) Max I/O
  * Massively concurrent access, slightly higher latencies

## Diagram
* 2TB for 12 hrs
  * Std EFS
    * $10
  * IA EFS
    * $0.83 cents
  * gp EBS
    * $3
  * EBS Cold HDD
    * $0.83 cents
  
[<img src="https://i.imgur.com/9GcuIz1.png">](https://i.imgur.com/9GcuIz1.png)

---

## Instance Store
* Temporary block-level storage (ephemeral)
* Physically attached to host computer
* Frequently changing data
  * Buffers, cache, scratch data, etc
* Ephemeral - goes away with instance
  * have another source for persistent data
  * Data is preserved during reboots
