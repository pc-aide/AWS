# Demo - Intro

## Acronym
* CW - CloudWatch
* ES - ElasticSearch
* IAM - Identity & Access Management
* O/P - OutPut
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
    * Enable Amazon Cognito authentication

[<img src="https://i.imgur.com/EdBTFJ9.png">](https://i.imgur.com/EdBTFJ9.png)

* Access policy
  * Domain access policy: 
  
[<img src="https://i.imgur.com/C8npr4h.png">](https://i.imgur.com/C8npr4h.png)

* Encryption
  * Encryption
    * CheckBox
      * Require HTTPS for all trafficto the domain
      * Node-to-node encryption
      * Enable encryption of dat at rest
      
[<img src="https://i.imgur.com/mB1a4vR.png">](https://i.imgur.com/mB1a4vR.png)

* Optional ElasticSearch cluster settings
  * Indices in request bodies
    * CheckBox
      * Allow APIs that can span multiple indices & bypass index-specific access policies
  * Fileddata cache allocation:
  * Max clause count:
  
[<img src="https://i.imgur.com/dbwBQUD.png">](https://i.imgur.com/dbwBQUD.png)

* Review (demo):

[<img src="https://i.imgur.com/Wfd9klK.png">](https://i.imgur.com/Wfd9klK.png)
[<img src="https://i.imgur.com/rOhV3Cc.png">](https://i.imgur.com/rOhV3Cc.png)

* O/P (demo):
  * Domain status: Loading
    * it'll take 10m

[<img src="https://i.imgur.com/oz9g5Rp.png">](https://i.imgur.com/oz9g5Rp.png)

* Use case
  * Analyzing & Visualizin real time data, ElasticSearch is probabley par of that answer
  
* CW\Log groups
  * Lambda

[<img src="https://i.imgur.com/vJSXcdk.png">](https://i.imgur.com/vJSXcdk.png)

* Choose Destination
  * Select account
    * RadioButton
      * This account
      * Another account
  * Amazon ES cluster:
  
[<img src="https://i.imgur.com/yO5dkGK.png">](https://i.imgur.com/yO5dkGK.png)

* Domain status: Active
  * Endpoint

[<img src="https://i.imgur.com/uh7bslK.png">](https://i.imgur.com/uh7bslK.png)

* Kibana

[<img src="https://i.imgur.com/zn8oh4G.png">](https://i.imgur.com/zn8oh4G.png)
[<img src="https://i.imgur.com/77bGf7W.png">](https://i.imgur.com/77bGf7W.png)
[<img src="https://i.imgur.com/nYYjnER.png">](https://i.imgur.com/nYYjnER.png)

* Try our sample data

[<img src="https://i.imgur.com/OsqerPH.png">](https://i.imgur.com/OsqerPH.png)
