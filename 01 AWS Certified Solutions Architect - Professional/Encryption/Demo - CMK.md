# Demo - CMK

## Acronym
* CMK - Customer Master Key

## Steps
### 01 - Create CMK KMS
* KMS\Customer managed keys\Create key
  * Key type: symmetric
    * A single encryption key that is used for both encrypt & decrypt operations
  * Advanced options: KMS
  * Alias: EC2Key
  * Descripton: use to encrypt EC2 volumes
  * Key administrators: KMSAdmin (Role)
  * Key usage: KMSUser (Role)
  * overview key policy
````json
{
  "Id": "key-consolepolicy-3",
  "Vesion": "2012-10-17",
  "statement": [
    {
      "Sid": "Enable IAM User Permissions",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam:018116317022:root"
      },
      "Action": "kms:*",
      "Resource": "*"
    },
    {
      "Sid": "Allow access for Key Administrators",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam:018116317022:role/KMSAdmin"
      },
      "Action": [
        "kms:Create*",
        "kms:Describe*",
        "kms:Enable*",
        "kms:List*",
        "kms:Put*",
        "kms:Update*",
        "kms:Revoke*",
        "kms:Disable*",
        "kms:Get*",
        "kms:Delete*",
        "kms:TagResource",
        "kms:UntagResource",
        "kms:ScheduleKeyDeletion",
        "kms:CancelKeyDeletion"
      ],
      "Resource": "*"
    },
    {
      "Sid": "Allow use of the key",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam:018116317022:role/KMSUser"
      },
      "Action": [
        "kms:Encrypt",
        "kms:Decrypt",
        "kms:ReEncrypt*",
        "kms:GenerateDataKey*",
        "kms:DescribeKey"
      ],
      "Resource": "*"
    },
    {
      "Sid": "Allow attachment of persistent resources",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam:018116317022:role/KMSUser"
      },
      "Action": [
        "kms:CreateGrant",
        "kms:ListGrants",
        "kms:RevokeGrant"
      ],
      "Resource": "*",
      "Condition": {
        "Bool": {
          "kms:GranIsForAWSResource": "true"
        }
      }
    }
  ]
}
````
[<img src="https://i.imgur.com/lKH62Pl.png">](https://i.imgur.com/lKH62Pl.png)

### 02 - Use CMK key
* Switch role: KMSUser

[<img src="https://i.imgur.com/Jat0oOu.png">](https://i.imgur.com/Jat0oOu.png)

* Launch EC2 Instance
  * Storage
    * Encryption: EC2Key
    
[<img src="https://i.imgur.com/kt4I8Wa.png">](https://i.imgur.com/kt4I8Wa.png)
[<img src="https://i.imgur.com/H4n90Sz.png">](https://i.imgur.com/H4n90Sz.png)
