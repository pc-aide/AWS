# ECS Task Placement & Constraints

## Acronym
* ECS - Elastic container service

## Doc
* [Amazon ECS task placement](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement.html)

## Intro
* When a task of type EC2 is launched, ECS must determinie where to place it, with the constraints of **CPU**,
  **RAM**, & **available port**
* Similarly, when a service scales in, ECS needs to determine which task to terminate
* To assist with this, you can define a **task placement strategy** & **task placement constraints**
* Note: this is only for ECS with EC2, not for Fargate
  
### Diagram
[<img src="https://i.imgur.com/pDVixW7.png">](https://i.imgur.com/pDVixW7.png)

---

## ECS Task Placement Process
* Task placement strategies are a best effort
* When Amazon ECS places tasks, it uses the following process to select container instances:
  1) Identify the instances that satisfy the **CPU, memory, & port** requirements in the task defintion
  2) Identify the instances that satisfy the task placement **constraints**
  3) Identify the instances that satisfy the task placement **strategies**
  4) Select the instances for task placement
  
---

## ECS Task Placement Strategies
### Binpack
 
  * Place tasks based on the least available amount of CPU or memory
  * This minimizes the number of instances in use (cost savings)
  * ex json:
````json
"placementStrategy""[
 {
  "field": "memory",
  "type": "binpack"
 }
]
````

### Diagram
[<img src="https://i.imgur.com/SCg2Fk2.png">](https://i.imgur.com/SCg2Fk2.png)

---

### Random
* Place the task randomly
* ex json
````json
"placementStrategy": [
 {
  "type": "random"
 }
]
````

### Diagram
[<img src="https://i.imgur.com/SCg2Fk2.png">](https://i.imgur.com/SCg2Fk2.png)

---

### Spead
* Place the task evenly based on the specified value
* Example: instanceld, attribute:ecs:availability-zone
* ex: json:
````json
"placementStrategy": [
 {
  "field": "attribute:ecs:availability-zone",
  "type": "spead"
 }
]
````

### Diagram
[<img src="https://i.imgur.com/yXyIjK4.png">](https://i.imgur.com/yXyIjK4.png)

---

### ECS Task Placement Strategies
* wraps up
  * You can mix them together
* ex-json:
````json
"placementStrategy": [
 {
  "field": "attribute"ecs"availability-zone",
  "type": "spead"
  },
  {
   "filed": "instanceId"
   "type": "spead"
  }
]
````
* or
* ex-json:
````json
"placementStrategy": [
 {
  "field": "attribute:ecs:availability-zone",
  "type": "spread"
 },
 {
  "field": "memory",
  "type": "binpack"
 }
]
````

---

## ECS Task Placement Constraints
* **DistinctInstance**: place each task on a different container instance
* ex-json:
````json
"placementContraints": [
 {
  "type": "dinstinctInstance"
 }
]
````
* **memberOf**: places task on instances that satisfy an expression
  * Uses the Cluster Query Language (advanced)
* ex-json:
````json
"strategyConstraints": [
 {
  "expession": "attribute:ecs.instance-type =~ t2.*",
  "type": "memberOf"
 }
]
````

---

## Demo
* cluster-demo\
  * create a new service
  
* cfg service
  * Launch type: EC2
  * Task definition: httpd
  * Revision: 3 (latest)
  * service name: demo-task-placement
  * Number of tasks: 2
  * Minimum healthy percent: 0
* Task placement
  * Placement templates: Custom
  * Type: BinPack (save cost) 
  * Field: Memory
  * Constraint
    * Type: DistinctInstance
    
[<img src="https://i.imgur.com/EZQBVDR.png">](https://i.imgur.com/EZQBVDR.png)
