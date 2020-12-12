# IAM

## Doc
* [Example IAM identity-based policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_examples.html)

## Acronym
* IAM - Identity & access management
* IdP - Identity Provider
* Creds - Credentials
* MFA - Multi-Factor Authentication
* cfg - Configuration

---

## Identities
1) IAM user
  * **Persons** or **application** wiht access to resrouces in AWS account
2) Existing Users
  * Federated from directory or IdP like Amazon Cognito, Facebook, Gooogle

---

## Creds
1) User & Pwd
  * Console access
    * Can disable or reset
2) AWS Access key
  * Programmatic access
    * Set inactive or delete
3) MFA cfg

---

## Policies for Permissions
1) Principal
  * principal is a **person** or **application** that can make a **request** for an **action** or **operation** on an AWS resource
2) Action
3) Resource
4) Condition (optional)

---

## Policies
* **Deny by default**
  * Allow must be present, no specific deny
* Everything in request must match a policy if something is not working check:
  1) Principal
  2) Action
  3) Resource
  4) Condition

---

## Inline Policy
* Embedded directly in an entity
* Policy is deleted when entity deleted
* Ensure policy only assigned to one entity
* Use managed policies for most cases

---

## Group Organization
1) Admins
2) Dev
3) Billing
* Limit
  * IAM user can belong to max 10 groups

### Diagram
[<img src="https://i.imgur.com/k5h0fGl.png">](https://i.imgur.com/k5h0fGl.png)

---

## IAM Polcies
* Anatomy of a policy: JSON
    * Action
    * Resource
    * Conditions
    * Policy variables

````json
{
  "version": "2012-10-17",
  "Statement" : [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:AttachVolume",
        "ec2:DetachVolume"
      ],
      "Resource": "arn:aws:ec2:*:*:instance/*",
      "Condition": {
        "StringEquals" : {"ec2:ResourceTag/Department": "Development"}
      }
    },
    {
      "Effect": "Allow",
      "Action": [
        "ec2:AttachVolume",
        "ec2:DetachVolume"
      ],
      "Resource": "arn:aws:ec2:*:*:volume/*",
      "Condition": {
        "StringEquals": {"ec2:ResourceTag/VolumeUser": "${aws:username}"}
      }
    }
  ]
}
````

* Explicit **DENY** has precedence over ALLOw
* Best practice: use least privilege for maximum security
    * Access advisor: See permissions granted & when last accessed
    * Access Analayzer: Analyzer resource that are shared with external entity
      * ex: s3
