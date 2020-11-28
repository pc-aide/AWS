# Auto Scaling

## Acronym
* CW - CloudWatch
* ELB - Elastic Load Balancer
* AZ - Availability Zone
* ASG - Auto Scaling Group
* AMI - Amazon Machine Image

## Scaling Policies
1) Simple/Step Scaling:
  * increase or decrease instances based on two CW alarms
2) Target Tracking:
  * select a metric & a target value, ASG will smartly adjust
    * Keep average CPU at 40%
    * Keep request count per target at 1k
* To scale based on RAM, you must use a **Custom** CloudWatch Metric

---

## Good to know
* **Spot Fleet support** (mix on Spot & On-Demand instances)
* To upgrade an AMI, must update the **launch configuration/template**
  * You must terminate instances manually
  * CloudFormation can help with that step 
* **Scheduled scaling actions**:
  * Modify the ASG settings (min/max/desired) at pre-defined time
  * Helpful when patterns are known in advance
* Lifecycle Hooks:
  * Perform actions before an instance is in service, or before it is terminated
  * Examples: cleanup, log extraction, special health checks

---

## Scaling Processes
* Launch:
  * Add a new EC2 to the group, increasing the capacity
* Terminate:
  * Removes an EC2 instance from the group, decreasing its capacity
* HealthCheck:
  * Checks the health of the instances
* ReplaceUnhealthy:
  * Terminate unhealthy instances & re-create them
* AZRebalance:
  * Balancer the number of EC2 instances across AZ
* AlarmNotification:
  * Accept notification from CloudWatch
* ScheduledActions:
  * Performs scheduled actions that you create
* AddToLoadBalancer:
  * Adds instances to the LB or target group
* We can suspend these processes!

---

## Health Checks
* Health checks available:
  * EC2 Status Checks
  * ELB Health Checks (HTTP)
* ASG will launch a new instance after terminationg an unhealthy one
* Make sure the health check is simple & checks the correct thing

## Diagram
[<img src="https://i.imgur.com/VUzprT3.png">](https://i.imgur.com/VUzprT3.png)
