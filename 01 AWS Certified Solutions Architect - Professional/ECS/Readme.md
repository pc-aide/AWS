# ECS

## Acronym
* ECS - Elastic Container Service
* VPC - Virtual Private Cloud
* SG - Security Group
* VM - Virtual Machine
* ENI - Elastic Network Interface
* EKS - Elastic Kubernetes Service
* SSM - System Manager
* ALB - Application Load Balancer
* IAM - Identity & Access Management
* ASG - Auto Scaling Group
* ECR: Elastic Container Registry

## Intro
* ECS is a container orchestration service
* ECS helps you run Docker containers on EC2 machines
* ECS is complicated, & made of:
  * "ECS Core": Running ECS on user-provisioned EC2 instances
  * Fargate: Running ECS tasks on AWS-provisoned compute (serverless)
  * EKS: Running ECS on AWS-powered Kubernetes (running on EC2)
  * ECR: Docker Container Registry hosted by AWS
* ECS & Docker are very popular for **microservices**

---

## What's Docker?
* Docker is a "container technology"
* Run a containerized application on any machine with Docker installed
* Containers allows our application to work the same way anywhere
* Containers are isolated from each other
* Control how much RAM/CPU is allocated to your container  
* Ability to restrict network rules
* More efficient than VMs
* Scale containers up & down very quickly (seconds)

---

## Use cases
* Run microservices
  * Ability to run multiple docker containers on the same machine
  * Easy service discovery features to enhance communication
  * Direct integration with ALBs
  * Auto scaling capability
* Run batch processing/scheduled tasks
  * Schedule ECS containers to run On-demand/Reserved/Spot instances
* Migrate application to the cloud
  * Dockerize legacy applications running on premise
  * Move Docker containers to run on ECS
  
---

## Concepts
* ECS cluster:
  * set of EC2 instances
* ECS service:
  * applications definitions running on ECS cluster
* ECS tasks + definition:
  * containers running to create the application
* ECS IAM roles:
  * roles assigned to tasks on interect with AWS

### Diagram
[<img src="https://i.imgur.com/ZdoNxye.png">](https://i.imgur.com/ZdoNxye.png)

---

## ALB integration
* ALB has a direct integration feature with ECS called "port mapping" or dynamic port
* This allows you to run multiple instances of the same application on the same EC2 machine
* Use cases:
  * Increased resiliency even if running on one EC2 instance
  * Maximize utilisation of CPU/cores
  * Ability ot perform rolling upgrades without impacting application uptime
  
### Diagram
[<img src="https://i.imgur.com/YiDaGcm.png">](https://i.imgur.com/YiDaGcm.png)

---

## Fargate
* When lauching an ECS Cluster, we have to create our EC2 instances
* If we need to scale, we need to add EC2 instances
* So we manage infrastructure...
* With Fargate, it's all Serverless!
* We don't provision EC2 instances
* We just create task definitions, & AWS will run our containers for us
* To scale, just increase the task number. Simple! No more EC2

---

## Security & Networking
* IAM security
  * EC2 Instances Role must have basic ECS permissions
  * ECS Task level should have an IAM Task Role (maximum security)
* Secrets & Configuration injection into parameters, environment variables:
  * Integration with SSM Parameter Store & Secrets Manager
* Tasks networking:
  * none: no network connectivity, no port mappings
  * bridge: use Docker's virtual container-based network
  * host: bypass Docker's network, uses the underlying host network interface
  * awsvpc: 
    * Every tasks launched on the instance gets its own ENI & a private IP address
    * Simplified networking, enhanced security, SGs, monitoring, VPC flow logs
    * Default mode for Fargate
    
---

## Service Auto Scaling
* CPU & RAM is tracked in CloudWatch at the ECS service level
* Target Tracking: target a specific average CloudWatch metric
* Step Scaling: scale based on CloudWatch alarms
* Scheduled Scaling: based on predictable changes
* ECS Service Scaling (task level) ≠ EC2 Auto Scaling (instance level)
* Fargate Auto Scaling is much easier to setup (because serverless)

---

## Spot Instances
* ECS Classic:
  * Can have the underlying EC2 instances as Spot Intances (managed by an ASG)
  * Instances may go into draining mode to remove running tasks
  * Good for cost savings, but will impact reliability
* Fargate: Spot Intances are available as of Dec 2019:
  * Specify minimum of tasks for on-demnand baseline workload
  * Add tasks running on Fargate Spot for cost-saving (can be reclaimed by AWS)
  * Regardless of On-demand or Spot, Fargate scales well based on load
