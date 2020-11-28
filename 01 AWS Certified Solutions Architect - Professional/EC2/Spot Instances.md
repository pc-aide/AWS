# Spot Instances

## Doc
* [Pricing Hitory (via Console)](https://ca-central-1.console.aws.amazon.com/ec2sp/v1/spot/dashboard?region=ca-central-1)

## Acronym
* ECS - Elastic Container Service
* ASG - Auto Scaling Group

## Intro
* Can get a discount of up to 90% compared to On-demand
* Define **max spot price** & get the instance while **current spot price** < max
  * The hourly spot price varies based on offer & capacity
  * If the current spot price > your max price you can choose to **stop** or **terminate** your instance with a 2 minutes grace period
* Other strategy: **Spot Block**
  * "block" spot instance during a specified time frame (1 to 6 hours) without interruptions
  * In rare situations, the instance may be reclaimed
* Used for **batch jobs, data analysis, or workloads are resilient ot failures**
* Not great for critical jobs or databases

---

## Pricing History
* AZ (price for Stop):
  * ca-central-1a | 0.0296$
  * ca-central-1b | 0.0297$ 
  * Versus 0.1110$ On-Demand
  * Data 11-02-2020
[<img src="https://i.imgur.com/TnN4eSR.png">](https://i.imgur.com/TnN4eSR.png)

* User-defined max price:

[<img src="https://i.imgur.com/dvRkAye.png">](https://i.imgur.com/dvRkAye.png)

---

## Spot Fleets
* Collection (Fleet) of Spot Instances & optionally on-demand instances
* Set a maximum price you're willing to pay per Spot Intances or all
* Can have a mix of instance type (M5.large, M5.xlarge, C5.2xlarge, etc...) 
* Supports: EC2 standalone, Auto Scaling Groups (launch template), ECS (underlying ASG), AWS Batch (Managed compute Environment)
* Soft limits:
  * Target capacity per Spot Fleet or EC2 fleet: 10k
  * Target capcity across all Spot Fleet & EC2 Fleet in a region: 100k
