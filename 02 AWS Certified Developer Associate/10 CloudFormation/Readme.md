# CloudFormation

## Acronym
* SG - Security Group
* EIP - Elastic IP
* LB - Load Balancer
* ELB - Elastic Load Balancer

## Doc

## Infrastructure as Code
* Currently, we have been doing a lot of manual work
* All this manual work will be very tohgh to reproduce:
    * In another region
    * in another aWS account
    * Within the same region if everything was delete
* Wouldn't it be grat, if all our infrastructure was... code?
* That code would be deployed & create/ update/ delete our infrastructure

---

## What is CloudFormation
* CloudFormation is a declarative way of outlining your AWS infrastructure, for any resources (most of them are supported)
* For example, within a CloudFormation template, you saiy:
    * I want a SG
    * I want 2 EC2 machines using this SG 
    * I want 2 EIPs for these EC2 machines
    * I want an S3 bucket
    * I want a LB (ELB) in front of these machines
* Then CloudFormation creates those for your, in the **right order**, with the **exact configuration** that yu specify

---

## Benefits of CloudFormation
* Infrastructure as code
    * No resources are manually created, which is excellent for control
    * The code can be version controlled for example using git
    * Changes to the infrastucture are reviewed through code
* Cost
    * Each resources within the stack is stagged with an identifier so you can easily see how much a stack costs you
    * You can estimate the costs of your resources using the CloudFormation template
    * Savings stategy: In Dev, you could automation deletion of templates at 5 PM & recreated at 8 AM, safely
* Productivity
    * Ability to destroy & re-create an infrastructure on the cloud on the fly
    * Automated generation of Diagram for your templates!
    * Declarative programming (no need to figure out ordering & orchestration)
* Seperation of concern: create many stacks for many apps, & many layers. 
    * Ex:
        * VPC stacks
        * Network stacks
        * App stacks
* Don't re-invent the wheel
    * Leverage existing templates on the web
    * Leverage the documentation
    
---

## How CloudFormation Works
* **Templates** have to be uploaded in S3 & then referenced in CloudFormation
* To update a template, we can't edit previous ones. We have to re-upload a new version of the template to AWS
* Stacks are identified by a name
* Deleting a stack deletes every single artifact that was created by CloudFormation

---

## Deploying CloudFormation templates
* Manual way:
    * Editing templates in the CloudFormation Designer
    * Using the console to input parameters, etc
* Automated way:
    * Editing templates in a YAML file
    * Using the AWS CLI to deploy the templates
    * Recommended way when you fully want to autmate your flow
    
---

## CloudFormation Building Blocks
* <ins>Templates components (one course section for each):</ins>:
    1) **Resources**: your AWS resources declared in the remplate (**mandatory**)
        * examples: EC2, SG, ELB, etc
    2) Parameters: the dynamic inputs for your template
    3) Mappings: the static variables for your template
    4) Outputs: References to what has been created
    5) Conditionals: List of conditions to perform resource creation
    6) Metadata
* <ins>Templates helpers:</ins>
    1) References
    2) Functions
    
---

## Note
* This is an intro to CloudFormation
    * It can take over 3 hours to properly learn & master CloudFormation
    * This section is meant so you get a good idea of how it works
    * We'll be slightly less hans-on than in other sections
