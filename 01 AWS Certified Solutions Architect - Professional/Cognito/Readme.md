# Cognito

## Acronym
* Idp - Identity Provider
* STS - Security Token Service
* cred - credential

## Intro
* Authenticate with 3<sup>rd</sup> party Idp
  * Amazon, Facebook, Gooogle
* Exchange toekn from Idp for Cognito token
  * Then get temporary cred from STS
  * Access resources in AWS account
* Cognito supports **unauthenticated profiles**
* Offload user management tasks to Cognito
  * Create user
  * Verification
  * Authentication
  * Password reset
* Scales to millions of users
