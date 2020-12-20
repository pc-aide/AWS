# Reserved Instance

## Acronym
* AZ - Availability zone
* u - unit

## Intro
* Price
  * Lower cost than on-demand instances
* Guaranteed Capacity (AZ)
  * No more errors about
    * InsufficientInstanceCapacity
  * Must specify AZ
  
---

## Part of agreement
1) Attributes
  * Instance type
    * e.g: t2.micro (t for bust), or c1.medium (c for cpu)
  * Region
    * US East
    * canada central
  * Tenancy
    * share or dedicated (host)
  * Platform
    * OS: Windows, Linux,& Mac
2) Commitment Term
  * 1 or 3 years
  * Longer term = larger discount
3) Payment
  * All upfront
  * Partial upfront
  * No upfront
  
### E.g
* Region: us-east-1
* On-demad
  * 4x m5 (instance type)
  * Price: ($0.10u/hr) * 4 = $0.40

* Mixed (2x reserved + 2x On-demand)
  * Price:
    * 2x Reserved: ($0.05u/hr) * (2) = $0.1
    * 2x on-demand: ($0.1u/hr) * (2) = $0.2
    * Sum: $0.3
    
---

## Additional Options for Reserved Instances
1) Scheduled
  * daily, weekly or monthly
  * start time & duration
2) Standard vs Convertible
  * modify instance type
    * e.g m5.2xlarge -> t2.micro
3) Regional vs Zonal    
  * Only zonal guarante capacity
