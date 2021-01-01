# Cost

## Doc
* [saving plans](https://aws.amazon.com/savingsplans/)

## Cost of EC2 Instances
1) Payment type
  * Dedicated host
  * On demand
  * Spot
  * Reserved Instance
    * upfornt
    * partial 
    * monthly
2) Instance type & size
  * type of familly
    * t2.micro
    * m5.large
    * etc
3) Storage
  * EBS
    * gpvX, where X={2,3}
    * cold HDD
    * ioX, where x={1,2}
    * Throughput optimized HDD
  * EFS
  * Instance Store
4) Network traffic

---

## EC2 Payment Types
1) On-demand
  * simple, pay as you go, you use 3h, so you pay for 3h
2) Saving plans (new models)
  * Commitment to **per-hour** spend
  * contract for 1 to 3 years
3) Reserved instances
  * Commitment to resurce
4) Spot instances
  * Very low rate, interruptible
5) Dedicated hosts
  * Single tenancy - entire machine
  * Most expensive
  
---

## EC2 Cost Factors
* Instances type  & size
  * Resources = cost
  * m5.24xl > m5.xl
* Storage 
  * EBS, EFS, Instance store
  * Charged until delete it
* Network traffic
  * Inbound, intra-region, & outbound data have different costs
