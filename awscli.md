# awscli

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
