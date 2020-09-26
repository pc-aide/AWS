# sts
* Security Token Service

## Swith
* help
    * aws sts help

## Syntax

## Examples
````bash
aws sts get-session-token --serial-number \<ar:aws:iam::...\> --token-code \<...\>
````
[<img src="https://i.imgur.com/oOpEawi.png">](https://i.imgur.com/oOpEawi.png)


* record this info for new profile mfa
````bash
aws configure --profile mfa
````
[<img src="https://i.imgur.com/X49fVAJ.png">](https://i.imgur.com/X49fVAJ.png)

* add this line for file credential

```bash
cat .aws/credentials | grep -A 3 mfa
````
[<img src="https://i.imgur.com/YBrYQJL.png">](https://i.imgur.com/YBrYQJL.png)

* test command with this profil mfa (temp)
````bash
aws s3 ls --profile mfa
````

[<img src="https://i.imgur.com/ig0xfFT.png">](https://i.imgur.com/ig0xfFT.png)
