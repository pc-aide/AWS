# ECS IAM Deep Dive & HANDS On

## Doc

## Acronym
* ECS - Elastic Container service
* ECR - Elastic Container registry

## Intro
* EC2 Instance Profile:
    * Ussed by the <ins>ECS agent</ins>
    * Makes API calls to ECS service
    * Send container logs to CloudWatch logs
    * Pull Docker image from ECR
* ECS Task role:
    * Allow each task to have a specific role
    * Use different roles for the different ECS Services you run 
    * Task Role is defined in the <ins>**task definition**</ins>

### Diagram
[<img src="https://i.imgur.com/UK33hAY.png">](https://i.imgur.com/UK33hAY.png)

---

## Demo
* IAM Roles: 
    * ecsInstanceRole
    * ecsServiceRole
        * Trusted entities
    * ecsTaskExecutionRole
    * AWSServiceRoleForECS

[<img src="https://i.imgur.com/Fr4N4k3.png">](https://i.imgur.com/Fr4N4k3.png)
[<img src="https://i.imgur.com/gRFpKq8.png">](https://i.imgur.com/gRFpKq8.png)
