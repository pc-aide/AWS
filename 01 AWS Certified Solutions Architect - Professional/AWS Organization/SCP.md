# SCP

## Acronym
* SCP - Service Control Policie
* OU - Organization Unit
* IAM - Identity Access Management

## Intro
* Cost & Security control
* Reduce attack surface 
* Limit potential charges
* Account or OU
  * When attach to an OU, SCP applies to all children (like OU in AD Windows)
* Scope
  * Affects all users & role including root user
  * Does not affect service-linked roles

---

## E.g
* Version the same (2012-10-17)
* One or more statement elements
* SID - optional user-provided identifier
* Effect - Allow or Deny
* Action - AWS services & action included in statement
* Resources affected by effect
* Condition  - specifies criteria that need to match
* Everything denied except t2.micro instances
* Need valid JSON for actual SCP
* e.g-01 of SCP:
````json
"Version": "2012-10-17",
"Statement": [
  {
    "Sid": "LimitEC2s",
    "Effect": "Deny",
    "Action": "ec2:RunInstances",
    "Resource": "arn:aws:ec2:*:*:instance/*",
    "Condition": {
      "StringNotEquals": {
        "ec2:InstanceType": "t2.micro"
      }
    }
  }
]
````

---

## SCPs
* Any action that isn't explicitly allowed by an SCP is implicitly **denied**
* Default **FullAWSAccess** SCP allows everything
* User must also have IAM policy to grant permission
* An explicit Deny in an SCP overrides any Allows from other SCPs
* Common use case for "blacklisting" services
* OU SCPs apply to all accounts in that OU
  * e.g: policy parent
  
---

## Demo
* AWS Organizations\Policies
  * SCP

[<img src="https://i.imgur.com/tTFhPHf.png">](https://i.imgur.com/tTFhPHf.png)

* SCPs
  * default: FullAWSAccess
    * Accounts - check out where this policies attach
    * OU - atttach too
  
[<img src="https://i.imgur.com/fhI4Dry.png">](https://i.imgur.com/fhI4Dry.png)
[<img src="https://i.imgur.com/9rYi2kL.png">](https://i.imgur.com/9rYi2kL.png)
[<img src="https://i.imgur.com/GJ4P1kp.png">](https://i.imgur.com/GJ4P1kp.png)

* Create policy:

[<img src="https://i.imgur.com/FchcF9F.png">](https://i.imgur.com/FchcF9F.png)

* Policy name: LimitEC2Micro
* Description: Only allow t2 micro instance to be lauched

[<img src="https://i.imgur.com/l52vwE7.png">](https://i.imgur.com/l52vwE7.png)

* Edit policy:
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "limitT2micro",
      "Effect": "Deny",
      "Action": "ec2:RunInstances",
      "Resource": "arn:aws:ec2:*:*:instance/*",
      "Condition": {
        "StringNotEquals": {
          "ec2:InstanceType": "t2.micro"
        }
      }
    }
  ]
}
````
[<img src="https://i.imgur.com/V59lEcY.png">](https://i.imgur.com/V59lEcY.png)

* Attach to
  * Account
    * select Accounts
    * Select SCPs
      * LimitEC2Micro -> Attach
    
[<img src="https://i.imgur.com/9UdmqqT.png">](https://i.imgur.com/9UdmqqT.png)
[<img src="https://i.imgur.com/yKhRXGG.png">](https://i.imgur.com/yKhRXGG.png)
[<img src="https://i.imgur.com/zsw8CiO.png">](https://i.imgur.com/zsw8CiO.png)
[<img src="https://i.imgur.com/zDB6DZ8.png">](https://i.imgur.com/zDB6DZ8.png)

### Test
* launch instance type not t2.micro:
  * e.g: t2.small
  
[<img src="https://i.imgur.com/vlBHQS4.png">](https://i.imgur.com/vlBHQS4.png)

#### Launch Failed
* msgError:
````txt
You are not authorized to perform this operation. Encoded authorization failure message: otB_oykdG7YeZSvyGmEc_xaXQwzobRST7Qtoj4lk-
L_jsp6jaRY95LDF9gZo4m4luLnxZsqDyzzuJbp36lliX_aB...
````

[<img src="https://i.imgur.com/LGaMFEM.png">](https://i.imgur.com/LGaMFEM.png)

---

## DenyInstanceTerminate
* New SCP
* Name: DenyInstanceTerminate
* Description: Deny terminate action of EC2 instance
* Policy:
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "NoTerminateEC2s",
      "Effect": "Deny",
      "Action": "ec2:TerminateInstances",
      "Resource": "arn:aws:ec2:*:*:instance/*"
    }
  ]
}
````

* Attach:

[<img src="https://i.imgur.com/noFRrHM.png">](https://i.imgur.com/noFRrHM.png)

* Policies inherited:

[<img src="https://i.imgur.com/Zu4kEZa.png">](https://i.imgur.com/Zu4kEZa.png)

### Test
* error - terminate instance:

[<img src="https://i.imgur.com/7Omx1fv.png">](https://i.imgur.com/7Omx1fv.png)
