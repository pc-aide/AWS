# Demo - Intro

## Acronym
* IAM - Identity & Access Management
* SAML - Security Assertion Markup Language
* SG - Security Group

## Console
* EBS - Elastic Block Storage
* ElasticSearch\Create a new domain

[<img src="https://i.imgur.com/apDsreO.png">](https://i.imgur.com/apDsreO.png)

* Choose deployment type
  * deployment type
    * RadioButton
      * Production
      * Development & testing
      * Custom
      
[<img src="https://i.imgur.com/G0URf6E.png">](https://i.imgur.com/G0URf6E.png)

* Version
  * ElasticSearch version:
  
[<img src="https://i.imgur.com/gefBAY4.png">](https://i.imgur.com/gefBAY4.png)

* Configure domain
  * ElasticSerach Domain name:
  * Custom endpoint
    * CheckBox
      * Enable custom endpoint
  * Data nodes
    * Instance type:
    * Number of nodes:
    
[<img src="https://i.imgur.com/eBhLbc9.png">](https://i.imgur.com/eBhLbc9.png)

* Data nodes storage
  * Data nodes storage type: 
  * EBS volume type:
  * EBS storage size per node:
  
[<img src="https://i.imgur.com/M1YX7Rv.png">](https://i.imgur.com/M1YX7Rv.png)

* Dedicated master nodes
  * Dedicated master nodes
    * CheckBox
      * Enable
  * Instance type
  * Number ofmaster nodes
* Snapt configuration
  * One a day, Amazon ElasticSearch Service takes an automated snapshot of your cluster
  
[<img src="https://i.imgur.com/mpPBE10.png">](https://i.imgur.com/mpPBE10.png)

* Diagram

[<img src="https://i.imgur.com/l6h4oJP.png">](https://i.imgur.com/l6h4oJP.png)

* Configure access & security
  * Network configuration
    * RadioButton
      * VPC access (Recommended)
      * Public access
    * VPC:
    * Subnet:
    * SGs:
    * IAM Role
    
[<img src="https://i.imgur.com/rB7TqN1.png">](https://i.imgur.com/rB7TqN1.png)

* Fine-grained access control - powered by Open Distro ElasticSeach
  * CheckBox
    * Enable fine-grained access control
    
[<img src="https://i.imgur.com/aCKeM6D.png">](https://i.imgur.com/aCKeM6D.png)

* SAML authentication for Kibana
  * CheckBox
    * Prepare SAML authentication
    
[<img src="https://i.imgur.com/oDnf8Th.png">](https://i.imgur.com/oDnf8Th.png)

* Amazon Cognito authentication
  * CheckBox
    * Enable Amazon Cognito au
