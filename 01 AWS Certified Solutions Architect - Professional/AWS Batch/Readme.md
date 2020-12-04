# AWS Batch

## Acronym
* VPC - Virtual Private Cloud
* AZ - Availability Zone
* HPC - High Performance Computing
* NAT - Network Address Translation
* ECS - Elastic Container Service
* EBS - Elastic Block Store
* CW - CloudWatch 
* ECR - Elastic Container Registry

## Intro
* Run batch jobs as Docker images
* Dynamic provisioning of the instances (EC2 & **Spot Instances**) - in VPC
* Optiomal quantity & type based  on volume & requirements
* No need to manage clusters, fully **serverless**
* You just pay for the underlying EC2 instances
* Example: batch process of images, running thousands of concurrent jobs
* by default, AWS batch -> one job per one EC2 instance
* Schedule Batch Jobs using CW Events
* Orchestrate Batch Jobs using AWS step Functions

---

## Solution Architecture
[<img src="https://i.imgur.com/EjrysJu.png">](https://i.imgur.com/EjrysJu.png)

---

## Batch vs Lambda
* Lambda:
  * Time limit: 900s or 15min
  * Limited runtimes
  * Limited temporry disk space: 512MB (/tmp/)
  * Serverless
* Batch:
  * No time limit
  * Any runtime as long as it's package as a Docker image
  * Rely on EBS/instance store for disk space
  * Relies on EC2 (can be managed by AWS)
  
---

## Compute Environments
* <ins>Managed Compute Environment:</ins>
  * AWS Batch managed the capacity & instance types within the environment
  * **You can choose On-Demand or Spot Instances**
  * You can set a miximum price for Spot Intances
  * Launched within your own VPC
    * If you launch within your own private subnet, make sure it has access to the ECS service
    * Either using NAT gateway/instance or using VPC Endpoints for ECS
* <ins>Unmanaged Compute Environment</ins>
  * You control & manage instance configuration, provisioning & scaling
  
---

## Managed Compute Environment
[<img src="https://i.imgur.com/KL5SjS3.png">](https://i.imgur.com/KL5SjS3.png)

---

## Multi Node Mode
* **Multi Node:** large scale, good for HPC
  * Leverages multiples EC2/ECS instances at the same time
  * Good for tightly coupled workloads
  * Represents a single job, & specified how many nodes to create for the job
  * 1 main node, & many child nodes
  * **Doesn't work with Spot Instances**
  * Works better if your EC2 launch mode is a placement group "cluster"
  
### Diagram
[<img src="https://i.imgur.com/A8WYHla.png">](https://i.imgur.com/A8WYHla.png)
