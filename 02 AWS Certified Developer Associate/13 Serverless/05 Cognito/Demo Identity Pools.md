# Demo Identity Pools

## Acronym
* IAM - Identity & Access Management

## Doc

## Console
* Cognito\Manage Identity pool
    * Identity pool name: Demo Identity Pool
    * CheckBox: Enable access to unauthenticated identities
    * Authentication providers
      * Cognito
        * User Pool ID: 
        * App client id: 
        
[<img src="https://i.imgur.com/dqbtxVO.png">](https://i.imgur.com/dqbtxVO.png)

* Identity the IAM roles
    * First IAM Role
      * Auth
    * Second
      * Unauth
      
[<img src="https://i.imgur.com/lfh3uug.png">](https://i.imgur.com/lfh3uug.png)

* Sample code
    * Platform
    * Download the AWS SDK

[<img src="https://i.imgur.com/YleYihZ.png">](https://i.imgur.com/YleYihZ.png)

* Dashboard

[<img src="https://i.imgur.com/hGKtaOk.png">](https://i.imgur.com/hGKtaOk.png)

* Identity browser

[<img src="https://i.imgur.com/7C6Qf6f.png">](https://i.imgur.com/7C6Qf6f.png)

* IAM role:
    1. Cognito_DemoIdentityPoolAuth_Role
    2. Cognito_DemoIdentityPoolUnauth_Role
    
[<img src="https://i.imgur.com/6WgsWJb.png">](https://i.imgur.com/6WgsWJb.png)

1. Cognito_DemoIdentityPoolAuth_Role
    * Cognito Identity
    * Cognito Sync
    * MObile Analytics
* so if i want a user to get acces for example s3:ReadOnly, just just to attach policy here
    
[<img src="https://i.imgur.com/HUSvxeN.png">](https://i.imgur.com/HUSvxeN.png)
[<img src="https://i.imgur.com/1wmmCsp.png">](https://i.imgur.com/1wmmCsp.png)

2. Cognito_DemoIdentityPoolUnauth_Role
    * Cognito Sync
    * Mobile Analytics
    
[<img src="https://i.imgur.com/aDTxWRG.png">](https://i.imgur.com/aDTxWRG.png)
[<img src="https://i.imgur.com/na2zkKn.png">](https://i.imgur.com/na2zkKn.png)

* Cognito\Identity pool
    * Edit identity pool
       * Push synchronization
       * Cognito Steams
       * Cognito Events
        * to run Lambda function in response to important events in Cognito
    
[<img src="https://i.imgur.com/UGAKnyx.png">](https://i.imgur.com/UGAKnyx.png)
