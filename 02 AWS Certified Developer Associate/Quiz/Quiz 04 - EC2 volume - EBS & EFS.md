# Quiz 04 - EC2 volume - EBS & EFS

## Questions
1) Your instance in us-east-1a just got terminated, and the attached EBS volume is now available.
   Your colleague tells you he can't seem to attach it to your instance in us-east-1b. 
   * He's missing IAM permissions
   * EBS volumes are region locked
   * EBS volumes are AZ locked
* [Answer](https://i.imgur.com/Jfr0agk.png)
2) You would like to have the same data being accessible as an NFS drive cross AZ on all your EC2 instances. What do you recommend?
    * Mount an EFS
    * Mount an EBS
    * Mount an Instance Store
* [Answer](https://i.imgur.com/CfTzSyO.png)
3) You would like to have a high-performance cache for your application that mustn't be shared. You don't mind losing the cache upon
   termination of your instance. Which storage mechanism do you recommend as a Solution Architect?
   * Instance Store
   * EBS
   * EFS
* [Answer](https://i.imgur.com/1FBR2y4.png)
4) You are running a high-performance database that requires an IOPS of 210,000 for its underlying filesystem. What do you recommend?
    * Use an eBS gp2 drive
    * Use an EBS IO1 drive
    * Use an EC2 Instance store
    * Use EFS
* [Answer](https://i.imgur.com/N7ieoW5.png)
