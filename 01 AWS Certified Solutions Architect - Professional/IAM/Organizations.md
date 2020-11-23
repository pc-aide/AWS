# Organizations

## Acronym
* IAM - Identity & Access Management
* STS - Security Token Service
* SSO - Single Sign-On
* OU - Organizational Units
* SCP - Service Control Policies

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
