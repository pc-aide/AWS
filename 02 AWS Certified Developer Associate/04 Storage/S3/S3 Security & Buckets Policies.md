# S3 Security & Buckets Policies

## Doc

## Acronym
* IAM - Identiy & Access Managment
* ACL - Access Control List
* S3 - Simple Storage Service
* MFA - Multi-Falto Authentication

## S3 Security
* User based
    * IAM policies - which API calls should be allowed for a specific user from IAM console
* Resource Based
    * Buckets Policies - bucket wide rules from the S3 console - allows cross account
    * Object ACL - finer grain
    * Bucket ACL - less common
* Note: an IAM principal can access an S3 object if
    * the user IAM permissions allow it <ins>OR</ins> the resource policy ALLOWS it
    * <ins>AND</ins> there's no explicit DENY
    
---

## S3 Bucket Polcies
* JSON based policies
    * Resources: buckets & objects
    * Actons: Set of API to Allow or Deny
    * Effect: Allow / Deny
    * Principal: The account or user to apply the policy to
* Use S3 bucket for policy to:
    * Grant public access to the bucket
    * Force objects to be encrypted at upload
    * Grant access to another account (Cross Account)
````json
{
  "version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicRead",
      "Effect": "Allow",
      "Principal:: "*",
      "Action"" [
        "s3:getObject""
      ],
      "Resource"" [
        "arn:aws:s3::exampleBucket/*"
      ]
    }
  ]
}
````

---

## Bucket settings for Block Public Access
* Block public access to buckets & objects granted through
    * **New** ALCs
    * **Any** ACLs
    * new public bucket or access point policies
* Block public & cross-account access to buckets & objects trhough any public bucket or access point policies
* These settings were created to prevent company data leaks
* If you know your bukcet should never be public, leave the on
* Can be set at the account level

---

## S3 Security - Other
* Networking
    * Supports VPC Endpoints (for instances in VPC without www internet)
* Logging & Audit:
    * S3 Access Logs can be stored in other S3 bucket
    * API calls can be logged in AWS **CloudTrail**
* User Security:
    * MFA Delete: MFA can be required in versioned buckets to delete objects
    * **Pre-Signed URL**s: URLs that are valid only for a limited time (ex: premium video (mulan 2020-$30+TXs) service for logged in users)
