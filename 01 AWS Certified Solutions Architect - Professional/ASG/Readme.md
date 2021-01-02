# ASG

## Acronym
* ASG - Auto Scaling Group

## Intro
* Started an ASG with launch configuration or launch template

---

## Lanch config vs lanch temp
* Summary with launch template vs lanch configuration, we have **more options** with lanch template than other option for our ASG
* AWS recommend that we should use **launch templates** instead of launch configurations to ensure that we can leverage the latest features of Amazon EC2, such as T2 Unlimited instances.


|n|Feature      |Lanch configuration | Lanch template|
|-|-------------|--------------------|---------------|
|1|Instance type|One choice          | many choices  |
|2|Versioning   | No (need copy)     | yes           |
|3|Storage      | One (default)      | Many choices  |
