# STS

## Acronym
* STS - Security Token Service
* MFA - Multi-Factor Authentication
* IAM - Identity & Access Management

## Doc
* [Providing access to an IAM user in another AWS account that you own](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_common-scenarios_aws-accounts.html)

## Intro
* Allow to grant limited & temporary access to AWS resources (up to 1 hour)
* **AssumeRole**: Assume roles within your account or corss account
* **AssumeRoleWithSAML**: return credentials for users logged with SAML
* **AssumeRoleWithWebIdenity**
    * return creds for users logged with an idP (Facebook Login, Google Login, OIDC compatible...)
    * AWS recommends against using this, & using **Cognito Identity Pools** instead
* **GetSessionToken**: for MFA, from a user or AWS account root user
* **GetFederationToken**: obtain temporary creds for a federated user
* **GetCallerIdenity**: return details about the IAM user or role used in the API call
* **DecodeAuthorizationMessage**: decode error message when an AWS API is denied

---

## Using STS to Assume a Role
* Define an IAM role within your account or cross-account
* Define which principals can access this IAM Role
* Uses AWS STS to retrieve credentials & impersonate the IAM Role you have access to (**AssumeRole API**)
* Temporary credentials can be valid between 15 minutes to 1 hour

### Diagram
[<img src="https://i.imgur.com/fcgdTQj.png">](https://i.imgur.com/fcgdTQj.png)

---

## Cross account access with STS
[<img src="https://i.imgur.com/YaHoT7D.png">](https://i.imgur.com/YaHoT7D.png)

---

## STS with MfA
* Use **GetSessionsToken** from STS
* Appropriate IAM policy using IAM Conditions
* aws:MultiFactorAuthPresent:true
````json
{
    "Version": "202-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ec2:StopInstances",
                "ec2:terminateInstances"
            ],
            "Resources": [
                "*"
            ],
            "Condition": {
                "Bool": {
                    "aws:MultiFactorAuthPresent": "true"
                }
            }
        }
    ]
}
````
* Reminder, GetSession Token returns:
    * Access ID
    * Secret Key
    * Session Token
    * Expiration data
