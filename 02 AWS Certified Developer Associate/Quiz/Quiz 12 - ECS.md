# Quiz 12 - ECS

## Questions
1) You are looking to run Microservices with Docker containers. Which service can help you manage these containers ?
    * ECR
    * ECS
    * Beanstalk
    * EC2
* [Answer](https://i.imgur.com/rsZBtyz.png)
2) Which ECS config must you enable in **/etc/ecs/ecs.config** to allow your ECS tasks to endorse IAM roles?
    * ECS_CLUSTER
    * ECS_ENGINE_AUTH_DATA
    * ECS_AVAILABLE_LOGGING_DRIVERS
    * ECS_ENABLE_TASK_IAM_ROLE
* [Answer](https://i.imgur.com/xiZn7E4.png)
3) You are looking to push Docker images into ECR with your AWS CodePipeline and CodeBuild. The last step fails with an authorization issue. What is the issue?
    * Open an AWS support ticket
    * Delete & re-create ECR repositories
    * Double check your IAM permissions for CodeBuild service
    * You first need to run an ECS instance
* [Answer](https://i.imgur.com/ALZk7bV.png)
4) You are looking to run multiple instances of the same application on the same EC2 instance and expose
   it with a load balancer. The application is available as a Docker container. You should use
    * CLB + Beanstalk
    * ALB + Beanstalk
    * CLB + ECS
    * ALB + ECS
* [Answer](https://i.imgur.com/NrpfjvW.png)
5) You are running a web application on ECS, the Docker image is stored on ECR, and trying to launch two containers
   of the same type on EC2. The first container starts, but the second one doesn't. You have checked and there's
   enough CPU and RAM available on the EC2 instance. What's the problem?
    * The EC2 instances has permissions issues with ECR & you must fix the IAM policy
    * The host port is defined in the task definition
    * The container port is definied in the task definition
    * EC2 instances can only run one container instance for each image
* [Answer](https://i.imgur.com/hWbLq1j.png)
6) You have started an EC2 instance and it's not registered with the ECS cluster. What's NOT a reason for this issue?
    * The ECS agent is not running
    * The AMI used isn't the AWS ECS AMI
    * The EC2 instance is missing IAM permissions
    * The security groups on the EC2 instance re misconfigured
* [Answer](https://i.imgur.com/Lggjk3C.png)
7) Which commands must be used to pull an image from ECR? (CLI v1)
    * ````bash
      dokcer login -u $AWS_ACCESS_KEY_ID -p $AWS_SECRET_ACCESS_KEY $ECR_URL
      docker pull $ECR_IMAGE_URL
      ````
    * ````bash
      dokcer login -u $AWS_USERNAME -p $AWS_PASSWORD $ECR_URL
      dokcer pull $ECR_IMAGE_URL
      ````
    * ````bash
      $(aws ecr get-login --no-include-email)
      dokcer pull $ECR_IMAGE_URL
      ````
    * ````bash
      dokcer build -t $ECR_URL .
      dokcer pull $ECR_IMAGE_URL
      ````
* [Answer](https://i.imgur.com/j28usOb.png)
8) You would like to run 4 ECS services on your ECS cluster, which need access to various services. What is the best practice?
    * Create an EC2 instance role with 4 policies & attach it to the EC2 instances in the ECS cluster
    * Create 4 EC2 instance roles & attach tehm to the EC2 instances in the ECS cluster
    * Create 1 ECS task role with 4 policies & attach it to each ECS task definition
    * Create 4 ECS task roles & attach tehm to the relevant ECS task defintion
* [Answer](https://i.imgur.com/Gk4Q3U4.png)
9) Which task cluster placement is the MOST cost-efficient?
    * binpack
    * spread
    * random
* [Answer](https://i.imgur.com/JDPmZGq.png)
