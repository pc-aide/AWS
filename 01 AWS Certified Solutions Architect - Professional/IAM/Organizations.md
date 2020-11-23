# Organizations

## Doc
* [Example service control policies](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples.html)
* [Policy evaluation logic](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html)

## Acronym
* IAM - Identity & Access Management
* STS - Security Token Service
* SSO - Single Sign-On
* OU - Organizational Units
* SCP - Service Control Policies
* RI - Reserved Instance
* EMR - Elastic MapReduce

## Intro
* Master accounts must invite Child Accounts
* Master accounts can create Child Accounts
* Master can access child accounts using:
  * CloudFormation StackSets to create IAM roles in target accounts
  * Assume the roles using the STS Cross Account capability
* Strategy to create a dedicated account for logging or security
* API is avaialble to automate AWS account creation
* Integration with AWS SSO

---

## Features
* Consolidated billing features:
  * Consolidated Billing across all accounts - single payment method
  * Pricing benefits from aggregated usage (volume discount for EC2, S3...)
* All Features (Default):
  * Includes consolidated billing features
  * You can use SCP
  * Invited accounts must approve enabling all features
  * Ability to apply an SCP to prevent member accounts from leaving the org
  * Can't switch back to Consolidated Billing Features only

---

## Multi Account Strategies
* Create accounts per **department**, per **cost center**, per **dev/test/prod**, based on
  **regulatory restrictions** (using SCP), for **better resource isolation** (ex:VPC), to have
  **separate per-account service limits**, isolated account for **logging**
* Multi Account vs One Account Multi VPC
* Use tagging standards for billing purposes
* Enable CloudTrail on all accounts, send logs to central S3 account
* Send CloudWatch Logs to central logging account
* Establish Cross Account Roles for Admin purposes

---

## OU - Examples
1) Business Units
2) Environmental Lifecycle
3) Project-based

### Diagram
[<img src="https://i.imgur.com/Plm0BUb.png">](https://i.imgur.com/Plm0BUb.png)

---

## AWS Organization
[<img src="https://i.imgur.com/WmHSZNZ.png">](https://i.imgur.com/WmHSZNZ.png)

---

## SCP
* Whitelist or blacklist IAM actions
* Applied at the **Root, OU** our **Account** level
* SCP is applied to all the **Users & Roles** of the Account, including Root
* The SCP does not affect service-linked roles
  * Service-linked roles enable other AWS services to integrate with AWS Organizations
    & can't be restricted by SCPs
* SCP must have explicit Allow (does not allow anything by default)
* Use cases:
  * Restrict access to certain services (for examples: can't user EMR)
  * Enforce PCI compliance by explicitly disabling services

---

## SCP Hierarchy
[<img src="https://i.imgur.com/SGqyJvq.png">](https://i.imgur.com/SGqyJvq.png)

---

## SCP Examples - Blacklist & Whitelist strategies
* Blacklist: 
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowAllActions",
      "Effect": "Allow",
      "Action": "*",
      "Resource": "*"
    },
    {
      "Sid": "DenyDynamoDB",
      "Effect": "Deny",
      "Action": "dynamodb:*",
      "Resource": "*"
    }
  ]
}
````
* Whitelist:
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Actions": [
        "ec2:*",
        "cloudwatch:*"
      ],
      "Resource": "*"
    }
  ]
}
````

---

## IAM Policy Evaluation Logic
[<img src="https://i.imgur.com/6hCTFrk.png">](https://i.imgur.com/6hCTFrk.png)

---

## Reserved Instances
* For billing purposes, the consolidated billing feature of AWS Organizations treats all the accounts
  in the organization as one account
* This means that **all accounts** in the organization can receive the hourly cost benefit of Reserved
  Instances that are purchased **by any other account**
* **The payer account (master account) of an organization** can turn off Reserved Instance (RI) discount
  & Savings Plans discount sharing for any accouonts in that organization, including the payer account
* This means that RIs & Saving Plans discounts aren't shared between any accounts that have sharing turned off
* To share an RI or Savings Plans discount with an account, both accounts must have sharing turned on
