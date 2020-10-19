# Demo Encryption SDK CLI

## Doc
* [Encryption SDK CLI](https://docs.aws.amazon.com/encryption-sdk/latest/developer-guide/crypto-cli.html)
* [Installing the AWS Encryption SDK CLI](https://docs.aws.amazon.com/encryption-sdk/latest/developer-guide/crypto-cli-install.html)
* [Examples of the AWS Encryption CLI](https://docs.aws.amazon.com/encryption-sdk/latest/developer-guide/crypto-cli-examples.html)

## Acronym
* ARN - Amazon Resource Name

## Intro
### Prereq
1. python > 2.7 or python > 3.4:

[<img src="https://i.imgur.com/akvkF4q.png">](https://i.imgur.com/akvkF4q.png)

2. python-pip (ver > 8.1): 
    * pip --version

[<img src="https://i.imgur.com/dWJwiuq.png">](https://i.imgur.com/dWJwiuq.png)
[<img src="https://i.imgur.com/pvOGZoG.png">](https://i.imgur.com/pvOGZoG.png)


### Install
* latest ver:
````bash
 pip install aws-encryption-sdk-cli
 ````
 [<img src="https://i.imgur.com/ys4gbaV.png">](https://i.imgur.com/ys4gbaV.png)
 
 * Version 
 ````bash
 aws-encryption-cli --version
 ````
 [<img src="https://i.imgur.com/Cp18GWp.png">](https://i.imgur.com/Cp18GWp.png)
 
 ### Example
 * cmk="arn"
 ````bash
 key = "arn:aws:kms:ca-central-1:427263915585:key/6a7e9076-461d-47c7-992f-eed92365b0f7"
 ````
 [<img src="https://i.imgur.com/YgQsdMo.png">](https://i.imgur.com/YgQsdMo.png)
 
 * Generate file over 1 MB (imagine)
 ````bash
 echo "super secret that over 1 MB" > hello.txt
 ````
[<img src="https://i.imgur.com/68pR7yl.png">](https://i.imgur.com/68pR7yl.png)

#### Encryption
* 
    * change $key = key="arn..." if choose another name
    * mkdir output if not exist
````bash
aws-encryption-cli --encrypt \
--input hello.txt \
--wrapping-keys key=$key \
--metadata-output metadata/ \
--output output/ 
````
[<img src="https://i.imgur.com/KdnCr6W.png">](https://i.imgur.com/KdnCr6W.png)
[<img src="https://i.imgur.com/M5rEWZP.png">](https://i.imgur.com/M5rEWZP.png)

* metadata (json-format):
    * json format (apt search --name-only ^jq$)
    * header: algorithm = AES256
    * provide_id
    * etc
````bash
cat metadata | jq
````

[<img src="blob:https://i.imgur.com/3LeZ2Ga.png">](https://i.imgur.com/3LeZ2Ga.png)
[<img src="https://i.imgur.com/qpowfQn.png">](https://i.imgur.com/qpowfQn.png)


* hello.txt.encrypted:
    * Binary file?

[<img src="https://i.imgur.com/B0vEFgE.png">](https://i.imgur.com/B0vEFgE.png)

* rm metadata - don't need

* cat hello.txt encrypted:

[<img src="https://i.imgur.com/B0vEFgE.png">](https://i.imgur.com/B0vEFgE.png)

#### Decryption
````bash
aws-encryption-cli --decrypt \
--input output/hello.txt.encrypted \
--wrapping-keys key=$key \
--discovery=false \
--metadata-output metadata \
--output decrypted/
````
[<img src="https://i.imgur.com/wHt6Yrd.png">](https://i.imgur.com/wHt6Yrd.png)

* cat metadata | jq
    * method: decrypt
    
[<img src="https://i.imgur.com/vnHi4eP.png">](https://i.imgur.com/vnHi4eP.png)

* cat decrypted/**hello.txt.encrypted.decrypted

[<img src="https://i.imgur.com/JCvcPsr.png">](https://i.imgur.com/JCvcPsr.png)
