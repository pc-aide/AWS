# KMS 

## Acronym
* KMS - Key Management Service
* IAM - Identity & Access Managment
* EBS - Elastic Block Store
* RDS - Relational Database Service
* SSM - System Manager Agent (SSM agent)
* CMK - Custom Master Key
* ECC - Elliptic Curve Cryptography

## Doc

## Intro
* Anytime your head "encryption" for an AWS service, it's mostlikely KMS
* Easy way to control access to your data, AWS manages keys for us
* Fully integrated with IAM for authorization
* Seamlessly integrated into:
    * EBS: encrypt volumes
    * S3: Server side encryption of objects
    * Redshift (data house): encryption of data
    * RDS: encryption of data
    * SSM : Parameter store
    * Etc...
* But you can also use the CLI/SDK

---

## KMS - CMK Type
* Symmetric (AES-256 keys)
    * First offering of KMS, single encryption key that is used to **Encrypt & Decrypt**
    * AWS services that are integrated with KMS use Symmetric CMKs
    * Necessary for envelope encryption
    * You never get access to the Key  unencrypted (must call KMS API to use)
* Asymmetric (RSA & ECCS key pairs)
    * **Public (encrypt)** & **Private** key (Decrypt) pair
    * Used for Encrypt/Decrypt, or Sign/Verify operations
    * The public key is downloadable, but you acces the Private Key unencrypted
        * ex: Key pair for EC2 for SSH !?
    * Use case: encryption outside of AWS by users who can't call the KMS API
    
----

## KMS 
* Able to fully manage the keys & policies:
    * Create 
    * Rotation policies
    * Diasable
    * Enable
* Able to audit key usage (using CloudTrail)
* Three types of CMKs:
    1. AWS Managed Service Default CMK: **free**
      * ex: AWS/EBS key
    2. User Keys created in KMS: **$1/month**
    3. User Keys imported (must be 256-bit symmetric key): **$1/month**
* + pay for API call to KMS ($0.03/10k calls)

---

## Use Cases
* Anytime you need to share sensitive information... use KMS
    * db passwords
    * Credentials to external service
    * Private Key of SSL certificates
* The value in KMS is that the CMK used to encrypt data can nerver be retrieved by the user,
  & the CMK can be rotated for extra security
* **Never eve store secrets in plaintext, espicially in your code**
* Encrypted secrets can be stored in the code/environment variables
* **KMS can only help in encrypting up to 4 KB of data per call**
* If data > 4 KB, use envelope encryption
* To give access to KMS to someone:
    * Make sure the Key Policy allows the user
    * Make sure the IAM Policy allows the API calls
    
---

## Copying Snapshots across regions
[<img src="https://i.imgur.com/YuMHypo.png">](https://i.imgur.com/YuMHypo.png)

---

## KMS Key Policies
* Control access to KMS keys, "similar" to S3 bucket policies
* Difference: you can't control access without them
* **Default KMS Key Policy**:
    * Created if you don't provide a specific KMS Key Policy
    * Complete access to the key to the root user = entire AWS account
    * Gives access to the IAM policies to the KMS key
* **Custom KMS Key Policy**:
    * Define users, roles that can access the KMS key
    * Define who can administer the key
    * Useful for cross-account access of your KMS key
    
---

## Copying Snapshots across accounts
1. Create a Snapshot, encrypted with your own CMK
2. Attach a KMS Key Policy to authorize cross-account access
* ex.: KMS Key Policy:
````json
{
    "Sid": "Allow use of the key with destination account",
    "Effect": "Allow",
    "Principals": {
        "AWS": "arn:aws:iam::ARGET-ACCOUNT-ID:role/ROLENAME"
    },
    "Action": [
        "kms:Decrypt",
        "kms:createGrant"
    ],
    "Resource": "*",
    "Condition": {
        "StringEquals": {
            "kms:ViaService": "ec2.REGION.amazonaws.com",
            "kms,CallerAccount": "TARGET-ACCOUNT-ID"
        }
    }
}
````
3. Share the encrypted snapshot
4. (in target) Create a copy of th Snapshot, encrypt it with a KMS Key in your account
5. Create a volume from the snapshot
