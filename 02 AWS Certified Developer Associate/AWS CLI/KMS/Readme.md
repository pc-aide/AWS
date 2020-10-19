# KMS

## Switchs
* aws kms help
* aws kms **encrypt** help

## Terminology 
* Binary file
    * cat FileEncrypted.base64 | base64 --decode > FileEncrypted

## Examples
### 01 Ecnryption
````bash
aws kms encrypt --key-id alias/Demo-KMS \
--plaintext fileb://ExampleSecretFile.txt \
--output text \
--query CiphertextBlob \
--region ca-central-1 > ExampleSecretFileEncrypted.base64
````
[<img src="https://i.imgur.com/CKyTwXx.png">](https://i.imgur.com/CKyTwXx.png)

### 02 Decryption
````bash
aws kms decrypt --ciphertext-blob fileb://ExampleSecretFileEncrypted \
--output text \
--query Plaintext > ExampleFileDecrypted.base64 \
--region ca-central-1
````
[<img src="https://i.imgur.com/nHgBe81.png">](https://i.imgur.com/nHgBe81.png)
