# Identity Pools

## Acronym
* IAM - Identity & Access Management
* CUP - Cognito User Pools
* STS - Security Token Service

## Doc

## Identity Pools (Federated Identities)
* Get identities for "users" so they obtain **temporary AWS credentials**
* Your identity pool (e.g identity source) can incude:
    * Public Providers (Login with Amazon, Facebook, Google, Apple)
    * Users in an Amazon Cognito user pool
    * OpenID Connect Providers & SAML Identity Providers
    * Developer Authenticated Identities (custom login server)
    * Cognito Identity Pools allow for <ins>unauthenticated (guest) access</ins>
* Users can then access AWS services directly or through API Gateway
    * The IAM policies applied to the credentials are defined in Cognito
    * They can be customized based on the user_id for fine grained control
    
### Diagram
[<img src="https://i.imgur.com/129cV0p.png">](https://i.imgur.com/129cV0p.png)

## Diagram with CUP
[<img src="https://i.imgur.com/fwQJhTg.png">](https://i.imgur.com/fwQJhTg.png)

---

## IAM Roles
* Default IAM roles for authenticated & guest users
* Define rules to choose the role for each user based on the user's ID
* You can partition your user's access using **policy variables**
* IAM credentials are obtained by Cognito Identity Pools through STS
* The roles must have a "trust" policy of Cognito Identity Pools

---

## Guest User example
````json
{
   "Version": "2012-10-17",
   "Statement": [
      {
         "Action": [
            "s3:GetObject"
         ],
         "Effect": "Allow",
         "Resource": [
            "arn:aws:s3:::mybucket/assets/my_picture.jpg"
         ]
      }
   ]
}
````

---

## Policy variable on S3
* Policy variable:
      * Ln8,16 - ${cognito-identity.amazonaws.com:sub}
````json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Action": ["s3:ListBucket"],
            "Effect": "Allow",
            "Resource": ["arn:aws:s3:::mybucket"],
            "Condition": {"StringLike": {"s3:prefix": ["${cognito-identity.amazonaws.com:sub}/*"]}}
        },
        {
            "Action":[
                "s3:GetObject",
                "s3:PutObject"
            ],
            "Effect": "Allow",
            "Resource": ["arn:aws:s3:::mybucket/${cognito-identity.amazonaws.com:sub}/*"]
        }
    ]
}
````

---

## DynamoDB
* Leading Keys
````json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "dynamodb.GetItem", "dynamodb:BatchGetItem", "dynamodb:Query",
                "dynamodb:PutItem", "dynamodb:UpdateItem", "dynamodb:DeleteItem",
                "dynamodb:BatchWriteItem"
            ],
            "Resource":[
                "arn:aws:dynamo:us-west-2:123456789012:table/MyTable"
            ],
            "Condition": {
                "ForAllValues:StringEquals": {
                    "dynamodb:LeadingKeys": [
                        "${cognito-identity.amazonaws.com:sub}"
                    ]
                }
            }
        }
    ]
}
````
