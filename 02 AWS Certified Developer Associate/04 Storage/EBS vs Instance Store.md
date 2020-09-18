# EBS vs Instance Store.md

## Doc

## Acronym

## Introduction
* Some instance don't come with Root EBS volumes
* Instead, they come with "Instance Store" (= **ephemeral** storage)
* Instance store is **physically** attached to the machine (EBS is a network drive)
* Pros:
    * Better I/O performance (no network)
    * Good for buffer / cache / sratch data / temporary content
    * Data survives reboots
* Cons:
    * On stop or termination, the instance store is lost
    * You can't resize the instance store
    * Backup must be operated by the user
* Local EC2 Instance Store
    * Physical disk attached to the physical server where your EC2 is
* Very High IOPS (because physical)
* Disks up to 7.5 TiB (can change over time), stripped to reach 30 TiB (can change over time...)
* Bloc Storage (just like EBS)
* Cannot be increased in size
* Risk of data loss if hardware fails

## Table
[<img src="https://i.imgur.com/csZhyWa.png">](https://i.imgur.com/csZhyWa.png)

## Demo
* Launch new instance\\<ami-xyz\>\
