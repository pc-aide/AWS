# ECS Auto Scaling

## Doc

## Acronym
* ECS - Elastic Container service
* ASG - Auto-Scaling Group

## Intro
* CPU & RAM is tracked in CloudWatch at the ECS service level
* **Target Tracking**: target a specific average CloudWatch metric
* **Step Scaling**: scale based on CloudWatch alarms
* **Scheduled Scaling**: based on predictable changes
* ECS service scaling (task level) ≠ EC2 auto scaling (instance level)
* Fargate auto scaling is much easier to setup (because serverless)

---

## ECS - Cluster Capacity Provider
* A capacity provider is used in association with a cluster to determine the infrastructure that a task runs on
    * For ECS & Fargate users, the Fargate & FARGATE_SPOT capacity providers are added automatically
    * For Amazon ECS on EC2, you need to associate the capacity provider with an auto-scaling group
* When yu run a task or a service, you define a capacity provider strategy, to prioritize in which provider to run
* This allows the capacity provider to automatically provision infrastructure for you

### Diagram
[<img src="https://i.imgur.com/ty24yNo.png">](https://i.imgur.com/ty24yNo.png)

---

## Demo
* cluster-demo\create capacity providers
    * Capacity provider name: Demo-Capacity
    * Auto Scaling group: ...
    * Target capacity %: 70
    * Managed termination protection: Disabled (demo)
    * Create
    
[<img src="https://i.imgur.com/43pGW2b.png">](https://i.imgur.com/43pGW2b.png)

* View in cluster:

[<img src="https://i.imgur.com/yqNUEa2.png">](https://i.imgur.com/yqNUEa2.png)

* ASG\Max capacity: 4
* Create a new service\
* cfg service
    * Launch type: **switch to capacity provider strategy**
    * Add provide\provider 1: Demo-capacity
    * Task definition: httpd
    * service name: httpd-service-capcity
    * Number of tasks: 10
    * Minimum healthy percent: 0
* Task placement\custom
    * Random
    
[<img src="https://i.imgur.com/UuA8gb4.png">](https://i.imgur.com/UuA8gb4.png)
[<img src="https://i.imgur.com/TMN8k2W.png">](https://i.imgur.com/TMN8k2W.png)

* Constraint is required

[<img src="https://i.imgur.com/5OvdSCU.png">](https://i.imgur.com/5OvdSCU.png)

* DistinctInstance (constraint)

[<img src="https://i.imgur.com/f4y1RUF.png">](https://i.imgur.com/f4y1RUF.png)

* 10x tasks

[<img src="https://i.imgur.com/rqgd3hY.png">](https://i.imgur.com/rqgd3hY.png)

* ASG\activity:

[<img src="https://i.imgur.com/0JikGFx.png">](https://i.imgur.com/0JikGFx.png)
