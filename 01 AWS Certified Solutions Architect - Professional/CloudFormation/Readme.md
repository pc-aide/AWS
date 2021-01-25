# CloudFormation

## Acronym
* ASG - Auto Scaling Group
* ALB - Application Load Balancer
* AMI - Amazon Machine Image
* CI/CD - Continuous Integration/Continuous Delivery
* DB - DynamoDB
* EBS - Elastic Block Store
* IaC - Infrastructure as Code
* IAM - Identity & Access Management
* HA - High Availability
* SAM - Serverless Application Model
* RDS - Relational Database Service

## Intro
* Simplify Deployments:
  * Easily simplify your infrastructure deployments all at once
* Replicate Quickly:
  * Templates allow for reuse in other regions to stand up HA applications
* Track Changes
  * CloudFormation tells you what you have deployed & tracks any changes
* IaC in AWS
* Portability of stacks across multiple accounts & regions
* Backbone of the Elastic Beanstalk service
* Backbone of the Service Catalog service
* Backbone of the SAM framework
* Must-know service as a developer/sysops/devops

---

## ASG
* CloudFormation manages the ASG, not the underlying EC2
* You can define "success conditions" for the launch of your EC2 instances using a **CreationPolicy**
* You can define "update strategies" for the update of your EC2 instances using an **UpdatePolicy**
* To update the underlying EC2 in an ASG, you have to create a **new launch configuration/launch template & use an UpdatePolicy**

### Diagram
[<img src="https://i.imgur.com/zI41hQZ.png">](https://i.imgur.com/zI41hQZ.png)
[<img src="https://i.imgur.com/EwB7wJL.png">](https://i.imgur.com/EwB7wJL.png)
[<img src="https://i.imgur.com/WYOmV9r.png">](https://i.imgur.com/WYOmV9r.png)
[<img src="https://i.imgur.com/aCb3cGS.png">](https://i.imgur.com/aCb3cGS.png)

---

## Retaining Data on Deletes
* You can put a DeletionPolicy on any resource to control what happens when the CloudFormation template is deleted
* **DeletionPolicy=Retain:**
  * Specify on resources to preserve/backup in case of CloudFormation deletes
  * To keep a resource, specify **Retain** (works for any resource/nested stack)
* **DeletionPolicy=Snapshot:**
  * EBS Volumes, ElastiCache Cluster, ElastiCache ReplicationGroup
  * RDS DBInstance, RDS DBCluster, Redshift Cluster
* **DeletePolicy=Delete (default behavior):**
  * Note:for**AWS::RDS::DBCluster** resources, the default policy is Snapshot
  * Note: to delete an S3 bucket, you need to first empty the bucket of its content
  
---

## IAM
* When deploying a CloudFormation stack
1) it use the permissions of our own IAM principal
2) OR assign an IAM role to the stack that can perform the actions
* If you create IAM resources, you need to explicitly provide a "capability" to CloudFormation **CAPABILITY_IAM** & **CAPABILITY_NAMED_IAM**

---

## Custom Resources (Lambda)
* You can define a Custom Resource in CloudFormation to address any of these use cases:
* An AWS resource is **not yet supported** (new service for example)
* An **On-Premise resource**
* Emptying an S3 bucket before being deleted
* Fetch an AMI id
* Anytining you want...!

### Diagram
[<img src="https://i.imgur.com/6cP3RqT.png">](https://i.imgur.com/6cP3RqT.png)

---

## Cross vs Nested Stacks
* Cross Stacks
  * Helpful when stacks have different lifecycles
  * Use Outputs Export & Fn::ImportValue
  * When you need to pass export values to many stacks (VPC Id, etc...)
* Nested Stacks
  * Helpful when components must be re-used
    * think module
  * Ex: re-use how to properly configure an ALB
  * The nested stack only is important to the higher level stack (it's not shared)
  * Each stacks, are going to be independently configured
  
### Diagram
[<img src="https://i.imgur.com/CwTTLY6.png">](https://i.imgur.com/CwTTLY6.png)


---

## Others Concepts
* CloudFormer
  * Create an AWS CloudFormation template from existing AWS resources
* ChangeSets
  * Generate & Preview the CloudFormation changes before they get applied
* StacksSets
  * Deploy a CloudFormation stack across multiple accounts & regions
* Stack Policies
  * Prevent accidental updates/deletes to stack resources
