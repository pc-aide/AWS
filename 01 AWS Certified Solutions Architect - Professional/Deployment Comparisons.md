# Deployment Comparisons

## Acronym
* AMI - Amazon Machine Image
* ASG - Auto Scaling Group
* ECS - Elastic Container Service
* ELB - Elastic Load Balancer
* SAM - Serverless Application Model

## Deployment Options
1) **Vanilla** EC2 with **User Data** (just for the first launch)
2) **Build** an **AMI** for things that are slow to install (runtimes, updates, tools), & use EC2 user data for quick runtime setup
3) **ASG** with launch template or launch configuration (AMI)
4) **CodeDeploy** (no new AMI - application deployments)
  * In-place on EC2
  * In-place on ASG
  * New instances on ASG
  * Traffic shifting for Lambda
  * New task set for ECS + traffic shifting
* Elastic Beanstalk
  * In-place all at once
  * Rolling upgrades (with or without additonal instances)
  * Immutable upgrades (new instances)
  * Blue/Green (entirely new stack)
    * Blue = old ver
    * Green = new ver
* OpsWorks
  * For chef/puppet stacks only
  * Can manage ELB & EC2 instances
  * Can't manage an ASG
* SAM Framework
  * Leverages CloudFormation & CodeDeploy
