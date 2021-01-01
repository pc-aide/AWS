# Placement Groups

## Doc
* [Placement groups](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html)

## Acronym
* AZ - Availability Zone

## 1/3 - Cluster Strategy
* Place instances close together
  * Single AZ
* Low latency, high throughput
* Only certain instance types
  * Best with enhanced networking
  * **Same instance type** for group
* Single launch request
* May experience insufficient capacity error

### Diagram
[<img src="https://i.imgur.com/XL9IN72.png">](https://i.imgur.com/XL9IN72.png)

---

## 2/3 - Partition Strategy
* Partition = rack data = servers
* Each rack has independent network & power sources
* Large distributed, replicated workloads
  * Topology aware applications

### Diagram
[<img src="https://i.imgur.com/nZy50yc.png">](https://i.imgur.com/nZy50yc.png)

---

## 3/3 - Spread Strategy
* Each instance in distinct rack
  * Independent network & power sources
* smal number of critical instances separate from each other

### Diagram
[<img src="https://i.imgur.com/h7BvvIQ.png">](https://i.imgur.com/h7BvvIQ.png)

--- 

## Rules 
* Name unique
  * Within your AWS account for region
* Can't merge
  * Delete existing groups then add instances to new single group
* One at a time
  * An instance can't span multiple placement groups
