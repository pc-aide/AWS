# Demo with CLI

## Acronym

## Doc

## Console
* KMS\AWS managed Keys
    * AWS\{acm,s3,dynamodb,codecommit,sns,sqs, etc} -managed by aWS
      * free
      * can't delete it
      * only to use for AWS services

[<img src="https://i.imgur.com/VxElNqt.png">](https://i.imgur.com/VxElNqt.png)
[<img src="https://i.imgur.com/7zj7Px5.png">](https://i.imgur.com/7zj7Px5.png)
[<img src="https://i.imgur.com/J7TcxAc.png">](https://i.imgur.com/J7TcxAc.png)

* Customer manager keys
    * $1 per month by key here

[<img src="https://i.imgur.com/sqHv8E8.png">](https://i.imgur.com/sqHv8E8.png)

* Custom key stores

[<img src="https://i.imgur.com/snzq7m8.png">](https://i.imgur.com/snzq7m8.png)

* Customer managed keys\create key
    * Key type: Symettric
    * Key material origin: KMS (generate our key)
    
[<img src="https://i.imgur.com/dwF715g.png">](https://i.imgur.com/dwF715g.png)

* Alias: Demo-KMS

[<img src="https://i.imgur.com/Mx6olZD.png">](https://i.imgur.com/Mx6olZD.png)

* Key policy\Key administrators
    * empty (default)
    
[<img src="https://i.imgur.com/9d33f55.png">](https://i.imgur.com/9d33f55.png)

* key usage permissions: empty (default)
    
[<img src="https://i.imgur.com/9zV2Tst.png">](https://i.imgur.com/9zV2Tst.png)

* Review & edit key policy
    * Default key policy - any users can have to acces this KMS key
    
[<img src="https://i.imgur.com/lZID4tD.png">](https://i.imgur.com/lZID4tD.png)
[<img src="https://i.imgur.com/m2Qo4ru.png">](https://i.imgur.com/m2Qo4ru.png)

* Demo-KMS
    * key rotation
      * Automatically rotate this CMK every year

[<img src="https://i.imgur.com/9hTqtl7.png">](https://i.imgur.com/9hTqtl7.png)
[<img src="https://i.imgur.com/tEEyx3Z.png">](https://i.imgur.com/tEEyx3Z.png)
[<img src="https://i.imgur.com/8248TUT.png">](https://i.imgur.com/8248TUT.png)

## Encrypt/Decrypt wiht own CMK
* Try now to encrypt & decrypt something with this CMK

* ExampleSecretFile.txt:
````txt
SuperSecretPassword
````

[<img src="https://i.imgur.com/rmnWZqX.png">](https://i.imgur.com/rmnWZqX.png)

* CLI
     * Windows
````powershell
# Encrypted
certutil -decode <fileEncrypted.base64> <fileEncrypted>
# Decrypted
certutil -decode <fileDecrypted.base64> <fileDecrypted.txt>
````
      
````bash
aws kms encrypt --key-id alias/Demo-KMS \
--plaintext fileb://ExampleSecretFile.txt \
--output text \
--query CiphertextBlob \
--region ca-central-1 > ExampleSecretFileEncrypted.base64
````
[<img src="https://i.imgur.com/CKyTwXx.png">](https://i.imgur.com/CKyTwXx.png)

* base64 decode (binary file)
````bash
cat ExampleSecretFileEncrypted | base64 --decode > ExampleSecretFileEncrypted
cat ExampleSecretFileEncrypted
````
[<img src="https://i.imgur.com/S7urgEV.png">](https://i.imgur.com/S7urgEV.png)

* Decryption
* CLI
````bash
aws kms decrypt --ciphertext-blob fileb://ExampleSecretFileEncrypted \
--output text \
--query Plaintext > ExampleFileDecrypted.base64 \
--region ca-central-1
````
[<img src="https://i.imgur.com/nHgBe81.png">](https://i.imgur.com/nHgBe81.png)

* base 64 decode
````bash
cat ExampleFileDecrypted.base64 | base64 --decode > ExampleFileDecrypted.txt
````
[<img src="https://i.imgur.com/w3Rczai.png">](https://i.imgur.com/w3Rczai.png)
