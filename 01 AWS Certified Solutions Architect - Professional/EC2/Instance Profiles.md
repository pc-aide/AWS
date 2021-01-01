# Instance Profiles

## Acronym
* IAM - Identity & Access Management

## Intro
1) Create Role
2) Attach some policies (json)
  * e.g access to an S3 bucket
3) Attach an IAM Role to your EC2 instance (instance profile)
4) SSH from your EC2 instance, we can acces a bucket

### Diagram
[<img src="https://i.imgur.com/dCq8Fgx.png">](https://i.imgur.com/dCq8Fgx.png)

---

## Summary
* Instance profiles
  * Assign **IAM role** to EC2 instance
  * No **credentials** to **embed**
  * Scale to multiple instances
  * Instant updates from role changes
