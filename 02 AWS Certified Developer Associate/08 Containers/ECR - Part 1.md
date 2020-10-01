# ECR - Part 1

## Acronym
* ECR - Elastic Container Registry
* IAM - Identity & access management

## Doc

## Intro
* So far we've been using Docker images from Docker Hub (public)
* ECR is a private Docker image repository
* Access is controlled through IAM (permission errors => policy)
* **AWS CLI v1 login** command (may be asked at the **exam**):
````bash
$(aws ecr get-login --no-include-email --region eu-west-1)
````
* **AWS CLI v2 loggin** command (newer, may also be asked at the exam -**pipe**):
````bash
aws ecr get-login-password \
  --region <region> \
  | docker login \
    --username aws \
    --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com
````
* Docker Push & Pull:
````docker
docker push <aws_account_id>.dkr.ecr.<region>.amazonaws.com/demo:latest
````
````docker
docker pull <aws_account_id>.dkr.ecr.<region>.amazonaws.com/demo:latest
````

---

## Demo
* ECR\Repositories:

[<img src="https://i.imgur.com/lOWA4q4.png">](https://i.imgur.com/lOWA4q4.png)

* Install docker on machine:
````bash
apt install -y docker.io
````
* check up version
````docker
docker --version
````
