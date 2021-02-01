# Snowball

## Acronym
* EB - Exabytes
* PB - Petabytes
* TB - Terabytes

## Intro
* Shipping container
* Snowball
  * size storage : 50-80 TB
  * 10G network
  * Physical data transport solution that helps moving TBs or PBs of data in or out of AWS
  * Alternative to moving data over the network (& paying network fees)
  * Secure, tamper resistant, use KMS 256 bit encryption
  * Trancking using SNS & text message. E-ink shipping label
  * Use case: large dta cloud migrations, DC decommission, disaster recovery
  * If it takes more than a week to transfer over the network, use Snowball device!
* a physical device to migrate your own data to cloud with Snowball
* how to use
  * transfert your data to snoball, & after you ship to Amazon (with track GPS)
  * our retrieve our data in your bucket
* Snowball edge (launched 2016):
  * Snowball Edges add **computational** capability to the device
  * 100 TB local storage
    * Storage optimized - 24 vCPU
    * Compute optimized - 52 vCPU & optional GPU
  * Suppors a custom EC2 AMI so you can perform processing on the go
  * Supports custom Lambda functions
  * Very usefull to pre-process the data while moving
  * Use case: data migration, image collation, IoT capture, machine learning
  * local compute equivalent to an EC2 m4.4xlarge instance
  * 10GBase-T, 10/25Gb SFP28, & 40Gb QSFP+ networking
  * Reggedized & rack-mountable
* Snowmobile
  * Up to 100 PB capacity
  * Transfert 1 EB = 1k PB = 1M TBs
  * GPStracking
  * Better than Snowball if you transfer more than 10 PB
  * Data encryption end-to-end
  * Dedicated security personnel

---

## Snowball Process
1. Request snowball devices from the AWS console for delivery
2. Install the snowball client on your servers
3. Connect the snowball to your servers & copy files using the client
4. Ship back the device when you're done (goes to the right AWS facility)
5. Data will be loaded into an S3 bucket
6. Snowball is completely wiped
7. Tracking is done using SNS, text messages & the AWS console

---

## Snowball vs Direct Upload
* Direct upload to S3:
  * bandwidth: ~10Gbit/s - dependent your connection to upload...

### Diagram
[<img src="https://i.imgur.com/0a5OL2m.png">](https://i.imgur.com/0a5OL2m.png)

---

### PNG
* Snowball:

[<img src="https://i.imgur.com/UGA0Phu.png">](https://i.imgur.com/UGA0Phu.png)

* Snowball edge:

[<img src="https://i.imgur.com/GRW8zyA.png">](https://i.imgur.com/GRW8zyA.png)

* AWS Snowmobile:

[<img src="https://i.imgur.com/KTQCBAV.png">](https://i.imgur.com/KTQCBAV.png)
