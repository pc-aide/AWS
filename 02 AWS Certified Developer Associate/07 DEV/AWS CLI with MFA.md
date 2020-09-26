# AWS CLI with MFA

## Doc

## Acronym
* API - application program 

## Intro
* To use MFA with the CLI, you must create a **temporary session**
* To do so, you must run the **STS GetSessionToke** API call
* **aws sts get-session-toke** --serial-number arn-of-the-mfa-device --token-code code-from-toke --duration-seconds 3600
````json
{
  "Credentials": {
    "SecretAccessKey": "secret-access-key",
    "SessionToke": "temporary-session-toke",
    "Expiration": "expiration-data-time",
    "AccessKeyID": "access-key-id"
  }
}
````

---

## Demo
* IAM\User\<UserNam\>\security credentials\
* Enabled your virtual MFA device
* take a copy of your **arn:aws:iam::...**

````bash
aws sts get-session-token --serial-number \<ar:aws:iam::...\> --token-code \<...\>
````
[<img src="https://i.imgur.com/oOpEawi.png">](https://i.imgur.com/oOpEawi.png)

* add your cred token .aws/credential
````bash
# ex for mfa (profile)
aws_session_toke = ...
````

[<img src="https://i.imgur.com/YBrYQJL.png">](https://i.imgur.com/YBrYQJL.png)

* test this profile mfa

````bash
aws s3 ls --profile mfa
````
[<img src="https://i.imgur.com/ig0xfFT.png">](https://i.imgur.com/ig0xfFT.png)
