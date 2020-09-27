# S3 MFA-Delete

## Acronym
* S3 - Simple Storage Service
* MFA - Multi-Factor Authentication

## Doc

## Intro
* MFA forces user to generate a code on a device (usually a mobile phone or hardware) before doing important operations on S3
* To use MFA-Delete, enable Versioning on the S3 bucket
* You will need MFA to
    * permanently delete an object version
    * suspen versioning on the bucket
* You won't need MFA for
    * enabling versioning
    * listing deleted versions
* Only the bucket owner (root account) can enabled/disable MFA-Delete
* MFA-Delete currently can only be **enabled** using the **CLI**
````bash
#Switch: Enabled & Disabled - First Disabled MFADelete
# Enabled MFADelet
aws s3api put-bucket-versioning --bucket mybucket --versioning-configuration Status=Enabled,MFADelete=Enabled --mfa "arn-of-mfa-device mfa-code" --profile root
# Disabled MFADelete
aws s3api put-bucket-versioning --bucket mybucket --versioning-configuration Status=Enabled,MFADelete=Disabled --mfa "arn-of-mfa-device mfa-code" --profile root
````
