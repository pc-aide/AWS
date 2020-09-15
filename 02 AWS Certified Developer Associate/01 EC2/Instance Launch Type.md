# Instance Launch Type

## Acronym
* BYOL - Bring your own license

## List
1) On Demand Instance
   * Short workload, predictable pricing
   * Pay for waht you use (billing per second, after the first minutes)
   * Has the highest cost but no upfront payment
   * No long term commitment
   * Recommended for short-term & interrupted workloads, where you can't predict how the application will behave
  
2) Reserved (min 1 year)
 
 a)
 
     * Reserved Instance: log workloads
     * Up to 75% discount compared to On-demand
     * Pay upfront for what you use with long term commitment
     * Reservation period can be 1 to 3 years
     * Reserve a specific instance type
     * Recommended for steady state usage applications (think database)
  
  b)
  
    * Convertible Reserved Intances: long workloads with flexible instances
    * Can change the EC2 instance type: e.g.: t2.micro -> t2.medium or the inverse
    * Up to 54% discount
    
    * Scheduled Reserved Instance: e.g.: every Thursday between 3 & 6 pm
    * launch within time window your reserve
    * When you require a fraction of day / week / month
    
  
  
3) Sport Instances: short workloads, for cheap, can lose instances (less reliable)
    * Can get a discount of up to 90% compared to On-demand
    * Instance that you can **"lose"** at any point of time if your max price is less than the currrent spot price
      * you bid : min 15$ & max 20$
    * The MOST cost-efficient instances in AWS
    * Useful for workloads that are resilient to failure
      * Batch jobs
      * Data analysis
      * Image processing
    * Not great for critical jobs or databases
    * Great combo: Reserved Instances for baseline + On-Demand & Sport for peaks (web page)

4) Dedicated Instances: no toher customers will share your hardware
    * Instances running on hardware that's dedicated to you
    * May share haedware with other instances in same account
    * No control over instance placement (can move hardware after stop / start)

5) Dedicated Hosts: book an entire physical server, control instance placement
    * Physical dedicated EC2 server for your use
    * Full control of EC2 Instance placement
    * Visibility into the underlying sockets / physical corers of the hardware
    * Allocated for your account for a 3 year period reservation
    * More expensive
    * Useful for software the have complicated licensing model (BYOL)
    * Or for companies that have strong regulatory or compliance needs
    
## Table
* Dedicated (Instance vs Host)

| Characteristic                                        | Dedicated<br>Instances | Dedicated<br>Host |
| ----------------------------------------------------- | ---------------------- | ----------------- |
| Enables the use of dedicated physical servers         | x                      | x                 |
| Per instance billing (subject to a $2 per region fee) | x                      |                   |
| Per host billing                                      |                        | x                 |
| Visibility of sockets, cores, host ID                 |                        | x                 |
| Affinity between a host an instance                   |                        | x                 |
| Targeted instance placement                           |                        | x                 |
| Automatic instance placement                          | x                      | x                 |
| Add capacity using an allocation request              |                        | x                 |

## which host ?
* On demand
    * Coming & staying in resort whenever we like, we pay the full price
* Reserved
    * Like planning ahead & if we plan to stay for a long time, we may get a good discount
* Sport instances
    * The hotel allows people to **bid** for the empty rooms & the highest bidder keeps the rooms. You **can get kicked out at any time**
    * if someone come & he's willing to pay more than they will kick you out
* Dedicated Hosts
    * We book an entire bulding of the resort
    
## Prcies Comparison
ex.: m4.large - us-east-1 :
    * vCPU: 2 | 8 Go RAM

| Price Type                                                                 | Price (per hour)                |
| -------------------------------------------------------------------------- | ------------------------------- |
| On-demand                                                                  | $0.10                           |
| Sport Instance (spot Price)                                                | $0.032 - $0.045 (up to 90% off) |
| Sport Block (1 to 6 hours)                                                 | ~ Sport Price                   |
| Reserved Instance (12 months) - no upfront                                 | $0.062                          |
| Reserved Instance (12 months) - all upfront                                | $0.058                          |
| Reserved Instance (36 months) - no upfront                                 | $0.043                          |
| Reserved **Convertible** Instance (12 months) - no upfront                 | $0.071                          |
| Reserved **Dedicated** Instance (12 months) - all upfront                  | $0.064                          |
| Reserved **Scheduled** Instance (recurring schedule on 12 months term)     | $0.090 - $0.095 (5%-10% off)    |
| Dedicated Host                                                             | On-demand price                 |
| Dedicated Host Reservation                                                 | Up to 70% off                   |
