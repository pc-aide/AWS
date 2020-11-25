# CloudHSM

## Acronym
* HSM - Hardware Security Module
* TDE - Transparent Data Encryption
* CRUD - Create, Read, Update & Delete 
* HA - High Availability
* SSE-C - Side-Server Encryption Custom
* SSL - Secure Sockets Layer
* TLS - Transport Layer Security
* AZ - Availability Zone
* KMS - Key Management Service

## Intro
* KMS -> AWS manages the **software** for encryption
* CloudHSM -> AWS provisions encryption **hardware**
* Dedicated Hardware
* You manage your own encryption keys entirely (not AWS)
* HSM device is tamper resistant, FIPS 140-2 Level 3 compliance
* Supports both symmetrics & **asymmetric** encryption (SSL/TLS keys)
* No free tier available
* Must use the CloudHSM Client Software
* Redshift supports CloudHSM for database encryption & key management
* **Good option to use with SSE-C encryption**

---

## Diagram
[<img src="https://i.imgur.com/Ecrcnr5.png">](https://i.imgur.com/Ecrcnr5.png)

---

## HA
* CloudHSM clusters are spread across Multi AZ (HA)
* Great for availability & durability

### Diagram
[<img src="https://i.imgur.com/DThS1Wl.png">](https://i.imgur.com/DThS1Wl.png)

---

## CloudHSM vs KMS
| Feature                    | KMS                                                                 | CloudHSM                                                                                           |
| -------------------------- | ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Tenancy                    | Uses multi-tenant key storage                                       | Single tenant key storage,<br>dedicated to one costomer                                            |
| keys                       | Keys owned & managed by AWS                                         | Customer managed keys                                                                              |
| Encryption                 | Supports only symmetric key<br>encryption                           | Supports both symmetrics &<br>assymmetric encryption                                               |
| Cryptographic acceleration | None                                                                | SSL/TLS Acceleration<br>Oracle TDE Acceleration                                                    |
| Key storage & management   | Accessible from multiple regions<br>Centralized management from IAM | Deployed & managed from a customer VPC<br>Accessible & can be shared across VPCs using VPC peering |
| Free tier availability     | yes                                                                 | no                                                                                                 |
