# Service Catalog

## Acronym
* IAM - Identity & Access Management

## Intro
* Users that are new to AWS have too many options, & may create stacks that are not compliant/in line with the rest of the organization
* Some users just want a quick **self-service portal** to launch a set of **authorized products** pre-defined **by admins** 
* Includes: VMs, databases, storage options, etc...
* Enter AWS Service Catalog!
* Create & manage catalogs of IT service that are approved on AWS
* The "products" are CloudFormation templates
* Ex: Virtual machine images, Servers, Software, Databases, Regions, IP address ranges
* **CloudFormation helps ensure consistency, & standardization by Admins**
* They are assigned to Portfolios (teams)
* Teams are presented a self-service portal where they can launch the products
* All the deployed products are centrally managed deployed services
* **Helps with governance, compliance, & consistency**
* Can give user access to launching products without requiring deep AWS knowledge
* Integrations with "self-service portals" such as ServiceNow

### Diagram
[<img src="https://i.imgur.com/J0wAjDZ.png">](https://i.imgur.com/J0wAjDZ.png)
