# IAM

## Acronym
* IAM - Identity & access management

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
