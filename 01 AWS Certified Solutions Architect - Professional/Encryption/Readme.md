# Encryption

## Acronym
* CMK - Customer Master Key
* KMS - Key Management Service
* HSM - Hardware security module

## Encryption Key Requirements
* Properly formed & unique
* Secure, controller access (NOT in your **database** or **application server**)
* Available - minimize wait time
* Durable - lost key means lost data
* Compliance for key management, audit use of keys

--

## KMS
* Managed service - centralized control
* HSM
* Which users administer & use keys
* Automatic yearly rotation
* Dynamically scales, 99.999 999 999% durability
* Integrated with AWS services
  * CloudTrail auditing
* Regional service
  * keys only available in region where generate them
  * Can't export keys from KMS
* Multi-tenant
  * HSM partitioned for use by multiple customers
  * If require single tenancy, use CloudHSM
  
### Diagram
[<img src="https://i.imgur.com/MSddC8l.png">](https://i.imgur.com/MSddC8l.png)
