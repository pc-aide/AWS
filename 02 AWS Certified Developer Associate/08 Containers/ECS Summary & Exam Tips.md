# ECS Summary & Exam Tips

## Doc

## Acronym
* ECS - Elastic Container service
* EKS - Elastic kubernetes service
* ALB - Application Load Balancer
* SG - Security Group
* IAM - Identity & access management
* ECR - Elastic Container Registry
* ENI - Elastic Network Interface

## Intro
* ECS is used to run Docker containers & has 3 flavors:
    1) ECS "classic": provision EC2 instance to run containers onto
    2) Fargate: ECS serverless, no more EC2 to provision
    3) EKS: managed kubernetes by AWS

---

## ECS Classic
* EC2 instances must be created
* We must configure the file **/etc/ecs/ecs.config** with the cluster name
* The EC2 instance must run an ECS agent
    * the ECS agent can be out of date
* EC2 instances can run multiple containers on the same type:
    * You must <ins>not</ins> specify a host port (only container port)
    * You should use ALB with the dynamic port mapping
    * The EC2 instances **SG** must **allow traffic** from the ALB on **all ports**
* ECS tasks can have IAM Roles to execute actions against AWS 
* SGs operate at the instance level, not task level

---

## ECR is used to store Docker Images
* ECR is tightly integrated with IAM
* AWS CLI v1 login command (may be asked at the exam):
````bash
$(aws ecr get-login --no-include-email --region eu-west-1)
````
* AWS CLI v2 login command (newer, may also be asked at the examp - pipe):
````bash
aws ecr get-login-password \
  ---region <region> \
  | docker login \
    --username aws \
    --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com
````
* Dokcer Push & Pull
    * push
````dokcer
docker push <1234567890>.dkr.ecr.<region>.amazonaws.com/demo:lates
```
    * pull
````dokcer
docker pull <1234567890>.dkr.ecr.<region>.amazonaws.com/demo:lates
```
* <ins>In case an EC2 instance (or you) can't pull a Docker image, check IAM</ins>

---

## Fargate
* Fargate is serverless (no EC2 to manage)
* AWS provisions containers for us & assigns them ENI
* Fargate containers are provisioned by the container spec (CPU/RAM)
* Fargate tasks can have IAM Roles to execute actions against AWS

---

## ECS Other
* ECS does integrate with CloudWatch logs:
    * You need to setup loggin at the task definition level
    * Each container will have a different log stream
    * **The EC2 Instance Profile needs to have the correct IAM permissions**
* Use IAM Task Roles for your tasks
* Task Placement Strategies: binpack, random, spread
* Service Auto Scaling with:
    * Target tracking
    * Step scaling
    * Scheduled
* Cluster Auto Scaling through Capacity Providers
