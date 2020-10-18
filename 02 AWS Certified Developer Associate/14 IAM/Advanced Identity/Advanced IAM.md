# Advanced IAM

## Acronym
* IAM - Identity & Access Management

## Doc

## Authorization Model Evaluation of Policies, simplified
1. If there's an explicit **DENY**, end decision & **DENY**
2. If there's an **ALLOW**, end decision with **ALLOW**
3. Else DENY

### Diagram
[<img src="https://i.imgur.com/cOuJPxV.png">](https://i.imgur.com/cOuJPxV.png)

---

## IAM Policies & S3 Bucket Policies
* IAM Policies are attached to users, roles, groups
* S3 Bucket Policies are attached to buckets
* When evaluation if an IAM Principal can perform an operation X on a bucket, the
  <ins> union</ins> of its assigned IAM Policies & S3 Bucket Policies will be evaluated
  
### Diagram
[<img src="https://i.imgur.com/DzmLvf8.png">](https://i.imgur.com/DzmLvf8.png)

---

## Example 1
* IAM Role attached to EC2 instance, <ins>authorizes RW to "my bucket"</ins>
* <ins>No S3 Bucket Policy attached</ins>
* Can I read/write to my bucket ?!
  * Answer: yes => EC2 instance can rad & write to "my bucket
  
---

## Example 2
* IAM Role attached to EC2 instance, <ins>authorizes RW to "my bucket"</ins>
* S3 Bucket Policy attached, <ins>explicit deny</ins> to the IAM Role
* Can I RW to "my bucket" ?!
    * Answer: no => EC2 instance <ins>**can't</ins> RW to "my bucket"
    
---

## Example 3
* IAM Role attached to EC2 instance, <ins>no S3 bucket permissions</ins>
    * no S3 bucket permissions: empty role
* S3 Bucket Policy attached, <ins>explicit RW allow</ins> to the IAM Role
* In this case, **can we to our EC2 instance RW to my Bucket?
    * Answer: yes => EC2 instance <ins>**can**</ins> RW to "my bucket"
      * it's not specified that i can do stuff in S3 (IAM Role)
      
---

## Example 4
* IAM Role attached to EC2 instance, <ins>explicit deny S3 bucket permissions</ins>
* S3 Bucket Policy attached, <ins>explicit RW allow</ins> to the IAM Role
* In this case, can we to our EC2 RW to my Bucket?
    * Answer: no => EC2 instance <ins>**can't**</ins> RW to "my bucket"
    
---

## Dynamic Policies with IAM
* How do you assign each user a /home/<user> folder in an S3 bucket?
* Option 1:
    * Create an IAM policies allowing Georges to have access to /home/Georges
    * Create an IAM policy allowing Sarah to have access to /home/Sarah
    * idem for another user
    * ... One policy per user
    * This doesn't scale
* Option 2:
    * Create one dynamic policy with IAM
    * Leverage the special policy variable ${aws:username}
    * exmple:
````json
{
  "Sid": "AllowAllS3ActionsInUserFolder",
  "Action": ["s3:*"],
  "Effect": "Allow",
  "Resource": ["arn:aws:s3:::my-company/home/${aws:username}/*"]
}
````

---

## Inline vs Managed Policies
* AWS Managed Policy
    * Maintained by AWS
    * Good for power users & administratora
    * Updated in case of new services/new APIs
* Customer Managed Policy
    * Best Practice, re-usable, can be applied to many principals
    * Version Controlled + rollback, central change management
* Inline
    * Strict one-to-one relationship between policy & principal
    * Policy is deleted if you delete the IAM principal
    
---

## Console
* IAM\Policies
    * Customer managed 
      * Take on - to see json
      * versions

[<img src="https://i.imgur.com/0POnSBv.png">](https://i.imgur.com/0POnSBv.png)
[<img src="https://i.imgur.com/nvayR1b.png">](https://i.imgur.com/nvayR1b.png)
[<img src="https://i.imgur.com/H0TvvTV.png">](https://i.imgur.com/H0TvvTV.png)
[<img src="https://i.imgur.com/913Noix.png">](https://i.imgur.com/913Noix.png)
[<img src="https://i.imgur.com/JSoHmik.png">](https://i.imgur.com/JSoHmik.png)
[<img src="https://i.imgur.com/9917CK1.png">](https://i.imgur.com/9917CK1.png)

* Inline policy
    * IAM\Users\<user>
    * Add inline policy
      * [Limit execeed 2048 bytes](https://i.imgur.com/AacltUS.png)
        * Maximum policy size of 2048 bytes exceed for user <user>
    
[<img src="https://i.imgur.com/WMvbvD7.png">](https://i.imgur.com/WMvbvD7.png)
[<img src="https://i.imgur.com/70iBmmz.png">](https://i.imgur.com/70iBmmz.png)
[<img src="https://i.imgur.com/sr18N8T.png">](https://i.imgur.com/sr18N8T.png)
