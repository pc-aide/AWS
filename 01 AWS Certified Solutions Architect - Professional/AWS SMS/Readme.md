# AWS SMS

## Acronym
* AMI - Amazon Machine Image
* DMS - Database Migration Service
* DR - Disaster Recovery
* EBS - Elastic Block Store
* SMS - Server Migration Service

## Intro
* Migrate enire <ins>VMs</ins> to AWS, improvement over EC2 VM Import/Export service
* That means the OS, the data, everything is kept intact
* After loading the VM onto EC2, then you can update the OS, the data, make an AMI
* Therefore SMS is used to Re-host
* Only works with <ins>VMware vSphere, Windows Hyper-V, & Azure VM</ins>
* Every replication creates an EBS snapshot/AMI ready for deplyment on EC2
* Every replication is incremental
* "One time migration", or "replication every interval" option

---

## On-Premise stategy with AWS
* Ability to download Amazon Linux 2 AMI as a VM (.iso format)
  * VMWare, KVM, VirtualBox (Oracle VM), Microsoft Hyper-V
* AWS Application Discovery Service
  * Gather inromation about your on-premise servers to plan a migration
  * Server utilization & dependency mappings
  * Track with AWS Migration Hub
* AWS VM Import/Export
  * Migrate existing applications into EC2
  * Create a DR repository strategy for your on-premise VMs
  * Can export back the VMs from EC2 to on-premise
* AWS SMS
  * Incremental replication of on-premise live servers to AWS
  * Migrates the entire VM into AWS  
* AWS DMS
  * replicate On-premise => AWS, AWS => AWS,AWS => On-premise
  * Works with various database technologies (Oracle, MySQL, DynamoDB, etc...)
