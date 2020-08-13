# awscli

## Acronym
* IAM - Manage access to AWS resources
* MFA - Multi-Factor Authentication

## Doc
* https://aws.amazon.com/premiumsupport/knowledge-center/s3-locate-credentials-error/

## Regex 
* ^ -	Start of string or start of line

## Apt seach
````Bash
apt seach --names-only ^aws
````
[<img src="https://i.imgur.com/LMcZ5c5.png">](https://i.imgur.com/LMcZ5c5.png)

## Help
````Bash
aws help
````
[<img src="https://i.imgur.com/44x09aB.png">](https://i.imgur.com/44x09aB.png)
### Available service
* s3

[<img src="https://i.imgur.com/VySmSjG.png">](https://i.imgur.com/VySmSjG.png)

## Credentials
* Error
````Bash
aws s3 cp demot.txt s3://bucket-dmo-01/demot.txt
````
[<img src="https://i.imgur.com/LusXlHF.png">](https://i.imgur.com/LusXlHF.png)
````Bash
aws configure list
````
[<img src="https://i.imgur.com/Mu4zqLV.png">](https://i.imgur.com/Mu4zqLV.png)

### IAM
* AWS Console\services\iam
* Tips : Activate MFA on your root account
[<img src="https://i.imgur.com/LjhLSVT.png">](https://i.imgur.com/LjhLSVT.png)

* Users\Add user

[<img src="https://i.imgur.com/v0obwMz.png">](https://i.imgur.com/v0obwMz.png)

* Set permissions

[<img src="https://i.imgur.com/XMSC7Jo.png">](https://i.imgur.com/XMSC7Jo.png)

* Add tags (optional)
  * Next

* Review

[<img src="https://i.imgur.com/is60iQu.png">](https://i.imgur.com/is60iQu.png)

* Publick key + Secret Key

[<img src="https://i.imgur.com/20Wwir8.png">](https://i.imgur.com/20Wwir8.png)

### Configure profile
````Bash
# Connect to your Server.Amazon(IMA)
aws configure --profile User-demo-s3
````
[<img src="https://i.imgur.com/9MU8cAg.png">](https://i.imgur.com/9MU8cAg.png)
````Bash
# ls --list segment
aws s3 ls
````
[<img src="https://i.imgur.com/hdL5gR8.png">](https://i.imgur.com/hdL5gR8.png)
