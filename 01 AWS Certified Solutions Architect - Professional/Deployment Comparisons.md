# Deployment Comparisons

## Acronym
* AMI - Amazon Machine Image
* ASG - Auto Scaling Group

## Deployment Options
1) **Vanilla** EC2 with **User Data** (just for the first launch)
2) **Build** an **AMI** for things that are slow to install (runtimes, updates, tools), & use EC2 user data for quick runtime setup
3) **ASG** with launch template or launch configuration (AMI)
4) **CodeDeploy** (no new AMI - application deployments)
  * In-place on EC2
