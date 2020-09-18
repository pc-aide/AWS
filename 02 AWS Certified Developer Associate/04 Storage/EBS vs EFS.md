# EBS vs EFS

## Acronym
* AZ - Availability Zone
* EBS - Elastic Block store
* EFS - Elastic File System
* IA - Infrequent Access

## Doc

## Introduction
* EBS volumes...
    * Can be attached to only one instance at a time
    * Are locked at the AZ level
    * gp2: I/O increases if the disk size increases
    * IO1: can increase I/O independently
* To migrate an EBS volume across AZ
    * Take a snapshot
    * Restore the snapshot to another AZ
    * EBS backups use I/O & you shouldn't run them while your application is handling a lot of traffic
* Root EBS volumes (/dev/xvda) of instances get terminated by default if the EC2 instance gets terminated (your can disable that)
    
### Topology
[<img src="https://i.imgur.com/SYY35t4.png">](https://i.imgur.com/SYY35t4.png)

---

EBS vs EFS 
* Mounting 100s of instance acroos AZ
* EFS share website files (WordPress)
* Only for Linux Instances (POSIX)
  * If you to use on-premise, sot use AWS VPN to mount efs on Ubunty (on-premise)
* EFS has a higher price point than EBS
* CAn leverage EFS-IA for cost savings
* Remember: EFS vs EBS vs Instance Store
