# Root User

## Doc
* [Tasks that require root user credentials](https://docs.aws.amazon.com/general/latest/gr/root-vs-iam.html#aws_tasks-that-require-root)

## Acronym
* IAM - Idenity & Access Management
* MFA - Multi-Factor Authentication
* SCP - Service Control Policy
* RI - Reserved Instance

## Actions that Only Root User Can Do
* Change account settings
  * account name, email, root password
* Change AWS support plan
* View certain tax invoices
* Restore IAM user permissions
* Register as a seller in RI marketplace
* Create CloudFront key pair
* Configure S3 bucket with MFA delete
* Resolve S3 bucket policy with invalid VPC ID or VPC endpoint ID
* Sign up for GovCloud
* Close AWS account

---

## Limit Root User Actions with SCPs
* Actions not listed in SCP are implicitly denied
* Lock down root users in member accounts
* Set guardrails with SCPs
  * SCPs pply to ALL users, uncluding root

### Diagram
[<img src="https://i.imgur.com/i40TUk4.png">](https://i.imgur.com/i40TUk4.png)
[<img src="https://i.imgur.com/sq4LBFO.png">](https://i.imgur.com/sq4LBFO.png)

---
