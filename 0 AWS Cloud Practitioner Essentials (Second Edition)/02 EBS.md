# EBS

## Acronym
* EBS - Elastic Block Store
* SSD - Solid-State drive
* HDD - Hard Drive Disk

## Overview - EBS Volumes
* Choose between HDD & SSD types
* Persisten & customizable block storage for EC2 instances
* Replicated in the same Availability zone
* Backup using Snapshots
* Easy & transparent Encryption
* Elastic volumes

## Drive Types
1) SSD
  * Faster

2) Magnetic volume
  * Logs
  * Cheaper
  
## Snapshots
  * Volumes
  * Re-create volume from snapshot at any time
  * Share a snapshot
  * Copy a snapshots to a different AWS Region for even greater disater recovery protection
    *E.g
      * Encrypt & share form Virgina to Tokyo your snapshots

## Encryption
* No additonal cost

## Elasticity
* EBS volumes have the ability to increase capacity
  * E.g
    * 50GB -> 16 TB without needing to stop the instances
* EBS volume can change to different types

## Demo
### One Disk (OS)
* AWS Console\EC2\

[<img src="https://i.imgur.com/BIsKSjp.png">](https://i.imgur.com/BIsKSjp.png)
