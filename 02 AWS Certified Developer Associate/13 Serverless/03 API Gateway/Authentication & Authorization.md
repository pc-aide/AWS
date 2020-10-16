# Authentication & Authorization

## Doc

## Acronym
* IAM - Identity & Access Managment
* VPC - Virtual Private Cloud

## Terminology
* Backend - background - the user can't see that
* Frontend - side of the user

## Security IAM Permissions
* create an IAM policy authorization & attach to User/Role
* **Authentication = IAM | Authorization = IAM Policy (allow|deny, actionAPI...)**
* Good to provide access within AWS (EC2, Lambda, IAM users...)
* Leverages "Sig v4" capability where IAM credential are in headers

### Diagram
[<img src="https://i.imgur.com/hlqbmE2.png">](https://i.imgur.com/hlqbmE2.png)

---

## Resource Policies
* **Resource policies** (similar to Lambda Resource Policy)
* Allow for Cross Account Access (combined with IAM Security)
* Ex:
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": [
          "arn:aws:iam::acount-id-2:user/Alice",
          "account-id-2"
        ]
      },
      "Action": "execute-api:Invoke",
      "Resource": [
        "arn:aws:execute-api:region:account-ide-1:api-id/stage/GET/pets"
      ]
    }
  ]
}
````
* Allow for a specific source IP address
* Allow for a VPC Endpoint

---

## Security Cognito User Pools
* Cognito fully manages user lifecycle, token expires automatically
* API Gateway verifies identity automatically from AWS Cognito
* No custom implementation required
* **Autentication = Cognito User Pools | Authorization = API Gateway Methods**

### Diagram
[<img src="https://i.imgur.com/4RHXo68.png">](https://i.imgur.com/4RHXo68.png)

---

## Security Lambda Authorizer (formerly Custom Authorizers)
* **Token-based authorizer** (bearer token) - ex: JWT (json Web Token) or Oauth
* A**request parameter-based** Lambda authorizer (**headers, query string**, stage var)
* Lambda must return an IAM policy for the user, result policy is cached
* **Authentication = External | Authorization = Lambda function**

### Diagram
[<img src="https://i.imgur.com/NkRuwPE.png">](https://i.imgur.com/NkRuwPE.png)

---

## Security - Summary
* IAM:
    * Great for users/roles already within your AWS account, **+ resource policy** for cross account
    * Handle authentication + authorization
    * Leverages Signature v4
* Customer Authorizer:
    * Great for 3<sup>rd</sup party tokens
    * Very flexible in terms of what IAM policy is returned
    * handle Authentication verification + Authrorization in the lambda function
    * Pay per lambda invocation, results are cached
* Cognitor User Pool:
    * You manage your own user pool (can be backed by Facebook, Google login etc...)
    * No need to write any custom code
    * Must implement authorization in the backend
  
---

## Console
* API Gateway\Resources
    * GET\Method request
  
[<img src="https://i.imgur.com/dSbtwrG.png">](https://i.imgur.com/dSbtwrG.png)
[<img src="https://i.imgur.com/zEJR3Jr.png">](https://i.imgur.com/zEJR3Jr.png)

* Authorization:
  * none
  * AWS_IAM -> Resource Policy
  
[<img src="https://i.imgur.com/UDyyijx.png">](https://i.imgur.com/UDyyijx.png)
[<img src="https://i.imgur.com/OTWLoLO.png">](https://i.imgur.com/OTWLoLO.png)

* Resource Policy
    * template (AWS Account Whitelist)
      * Remplace: otherAWSAccountID
    
[<img src="https://i.imgur.com/IJWJsIg.png">](https://i.imgur.com/IJWJsIg.png)

* Resource Policy
    * IP Range Blacklist
    
[<img src="https://i.imgur.com/jVAIDD1.png">](https://i.imgur.com/jVAIDD1.png)

* Resouce Policy
    * Source VPC Whitelist
    
[<img src="https://i.imgur.com/M2TmeGn.png">](https://i.imgur.com/M2TmeGn.png)

* Authorizers
    * Createe New Authorizer
    
[<img src="https://i.imgur.com/8oCxbSN.png">](https://i.imgur.com/8oCxbSN.png)
