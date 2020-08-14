# Auto Scaling

## Acronym
* EC2 - Elastic Compute Cloud
* VPC - Virtual Private Cloud
* AMI - Amazon Machine Image

## What is Auto Scaling?
* Auto Scaling helps you ensure that you have the correct
  number of Amazon EC2 instances available to handle the load
  for your application
    * Minimizing Cost

## Monitoring Resource Performance
[<img src="https://i.imgur.com/rjpzThV.png">](https://i.imgur.com/rjpzThV.png)

## Capacity Management
### Default (no Auto Scaling)

[<img src="https://i.imgur.com/orSnsMK.png">](https://i.imgur.com/orSnsMK.png)

   * Cloud Wacth to measure EC2 reource requirements
      * Wednesday requiring the most capacity
      * Saturday the least

### Unused Capacity

[<img src="https://i.imgur.com/Y0a53sq.png">](https://i.imgur.com/Y0a53sq.png)

   * Our Costs are not optimized


### Over Capacity

[<img src="https://i.imgur.com/qYbrU4T.png">](https://i.imgur.com/qYbrU4T.png)
* We are under capacity on certain days
* if we don't solver our capacity problem
  * Our application cloud under perform or potentially even time-out for the user

### Auto Scaling
[<img src="https://i.imgur.com/c8Z6nm6.png">](https://i.imgur.com/c8Z6nm6.png)
* This allows you to maintain performance
* Minimize cost

## Scaling Out & Scaling In
[<img src="https://i.imgur.com/NCSONHz.png">](https://i.imgur.com/NCSONHz.png)

## 3 Components required for auto scaling
1) Lauch Configuration
  * What?
    * AMI
    * Instance type
    * Security Groups
    * Roles

2) Auto Scaling Group
  * Where?
    * VPC & Subnet(s)
    * Load balancer
    * Minimum instances
    * Maximum instance
    * Desired capacity
    
3) Auto Scaling Policy
  * When?
    * Scheduled
    * On-demand
    * Scale-out policy
    * Scale-in policy

## Dynamic Auto Scaling
[<img src="https://i.imgur.com/03RDtqQ.png">](https://i.imgur.com/03RDtqQ.png)
* CloudWatch\Create Alarm triggers
    * Auto Scaling Event
    * Scale Out or Scale In -> EC2 instances in the environment

## CloudWatch Alarm for Auto Scaling
[<img src="https://i.imgur.com/BrkESs0.png">](https://i.imgur.com/BrkESs0.png)
