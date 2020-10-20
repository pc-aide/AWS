# SSM

## Acronym
* SSM - Simple System Manager
* KMS - Key Manager Service
* IAM - Identity & Access Management
* CW - CloudWatch

## Doc

## SSM Parameter Store
* Secure storage for configuration & secrets
* Optional Seamless Encryption using KMS
* Serverless, scalable, durable, easy SDK
* Version tracking of configurations/secrets
* Configuration managment using path & IAM
* Notifications with CloudWatch Events
* Integration with CloudFormation

### Diagram
[<img src="https://i.imgur.com/V9XQioN.png">](https://i.imgur.com/V9XQioN.png)

---

## SSM Parameter Store Hierarchy
* /my-department/
    * my-app/
      * dev/
        * db-url
        * db-password
      * prod/
        * db-url
        * db-password
    * other-app/
* /other-department/
* /aws/reference/secretsmanager/secret_ID_in_Secrets_Manager
* /aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2

### Diagram
[<img src="https://i.imgur.com/fuA2zt9.png">](https://i.imgur.com/fuA2zt9.png)

---

## Std & advanced parameter tiers
|                                                                                      | Standard                                                                          | Advanced                                                                                                       |
| ------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Total number of parameters<br>allowed<br>(per AWS account &<br>Region)               | 10k                                                                               | 100k                                                                                                           |
| Maximum size of a<br>parameter value                                                 | 4 KB                                                                              | 8 KB                                                                                                           |
| Parameter policies available                                                         | No                                                                                | Yes                                                                                                            |
| Cost                                                                                 | No additional charge                                                              | Charges apply                                                                                                  |
| Storeage Pricing                                                                     | Free                                                                              | $0.05 per advanced parameter per<br>month                                                                      |
| API Interaction Pricing<br>(higher throughput = up to<br>1k Transactions per second) | Standard Throughput: free<br>Higher Throughput: $0.05 per 10k<br>API interactions | Standard Throughput: $0.05 per 10k<br>API interactions<br>Higher Throughput: $0.05 per 10k<br>API interactions |

---

## Parameters Policies (for advanced parameters)
* Allow to assign a TTL to a parameter (expiration data) to force updating or deleting sensitive data such as passwords
* Can assign multiple policies at a time
* ex: **Expiration (to delete a parameter**)
````json
{
  "Type": "Expiration",
  "Version": "1.0",
  "Attributes": {
    "Timestamp": "2020-12-02T21:34:33.000Z"
  }
}
````
* ex: **ExpirationNotification (CW Events)**
````json
{
  "Type": "ExpirationNotification",
  "Version": "1.0",
  "Attributes": {
    "Before": "15",
    "Unit": "Days"
  }
}
````
* ex: **NoChangeNotification (CW Events)**
````json
{
  "Type": "NoChangeNotification",
  "Version": "1.0",
  "Attributes": {
    "After": "20",
    "Unit": "Days"
  }
}
````
