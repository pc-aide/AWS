# AWS CLI STS Decode Errors

## Doc

## Acronym

## URLs
* [decode-authorization-message](https://docs.aws.amazon.com/cli/latest/reference/sts/decode-authorization-message.html)

## Intro
* When yur run API calls & they fail, you can get a long error message
* This error message can be decoded using the **STS** command line:
* sts **decode-authorization-message**

### Demo

* ex:
````text
# AWS CLI:
aws ec2 run-instances --dry-run --image-id ami-020caff809d5a5307 --instance-type t2.micro

# Error
An error occurred (UnauthorizedOperation) when calling the RunInstances operation: You are not authorized to perform this operation.
Encoded authorization failure message:
m-yNX1GWpvhAQbNfWjiqQrxo9wFerxnJD63lNghsGxQ-EnQltKQVzbXXJIRyUxJut33pczHMxrEmBJOSQwwYHf3xPfnFm1gIew6uLQCF8Hr-_j5uY4vGddQIIyGD7IntewAaxHpjQ16qAHmd2s9Q569wQazjNjS27miyr-z-XSkLDqwU7btVCJ6tWvgnIcQaUlcVdz1VpqJ6G-5DoXr93G3YNPrW1N-u5MmISKGM_yZhZ116QjggcLhCenjCR7eOhdTrEJ8anO6r5fov3CFEJmzrvGgqLPIUmWwX_sI1DsIwZ1rYjubcU_3ZJVK6SYxlV-jivtXutPt1O0xR05B-119iIX4-L-EDRZFNPEZbsHXHA5CD0JA5um2OVmy2M0_D13xWBC3_5tYTLE11dSTpz-cTnAQwTyFe-qk-BlWLRXuLNSzEzodZZKzqzN5KPjwvprGBd4CNmBBhybr-qFdFDCy6KX4tpKw-CPhL8XG67UUOz0wyJZzJjs3m2WPTgLko-vhr8VrdqW_I9S-jZM1REuzLNmf8vJzZEQ-smFTek-Xt_CWaQLvDX1DAqeyXObbeln0wpjaHNdauNx7V2Gk7sSzS0ky24S8TLlZ3dUbXMVVEV0q83afRHwg5IMuyLK9TcaQhXJe9gmDS6ZTZhzpq0d7YobcVW4ZThgv9xn4z5n5q_qnVKYUqSuAkEQ
````

#### Decode
* syntax
    * aws sts decode-authorization-message --encoded-message \<MessageError\>

````bash
aws sts decode-authorization-message --encoded-message 5oIg0yAmdaR7Q-RqDSVtv3lOY7I8x3J51IMi-Zsxk9RMck8m2_q-MX-xM2jwcE4PvZK3R1zsvPX8dovhxn-6re5YFKChFj6nmnntcmMzxIDTFD8CqblmU4rPbwRFlyudXi3JEWfipuKerY_jVqihT1sIeVoFZ_2uIryF46EqVGER38LlKxDwlj7Yb9LXUvq13v7MlGRSEpELB1meQ_gXAh_n-pNTXI7U_zw2UnTBIPb9ZJo2yKfrVl5PxrmvMzX_6ut7Qg1FYpP9jXlAmhXfAeFa2fgcpSpTGmO0d9IUq-WpQaBTltkUUES286C418ZyHr6vrkDnqzSF9YHtxEBszUD3rcpdIHmNhbnB1_oPKCTcHSWt4PSoiAKuRXMr2BYQzylC0hHsM_W8cX8utGa-4TipE3bMl161eoQZZGcmGN3_rSME4mb6SgBnKxVznQoCFso8tH8K7HczVOomSSQdW4sUMbKZuG4_JLZ18569izA42msGPOWmJ317Ieh6ePAf5GAnFSIRkR_uZX18z2jUtHQ33lGzbWdhUsy25l6v8nBAhq8u1qE_OUbI_K1SrZvzl5lJELJb9LoAK_-g_1b_TRTIRT5On8I5fM7z6PSjzl6pQHn5uAzCfcQcNkaE6obfvOYa3PzLtnVhblqvOhn3mO-sHA_D2Y_5iFOp_vgS1KSVL1fzdB8JEU1SNg
````
[<img src="https://i.imgur.com/AHc2bys.png">](https://i.imgur.com/AHc2bys.png)

* add IAM policy

[<img src="https://i.imgur.com/hdAnwoK.png">](https://i.imgur.com/hdAnwoK.png)

* service: STS
* Actions: Write\DecodeAuthorizationMessage
* Review policy
* Name: STSDecodeAuthorizationMessage

[<img src="https://i.imgur.com/w3Wupct.png">](https://i.imgur.com/w3Wupct.png)

* Try again our aws sts decode...

[<img src="https://i.imgur.com/apQYy3q.png">](https://i.imgur.com/apQYy3q.png)

* Used visual studio code for syntax + reformat:
    * syntax-json: Ctrl + K M
    * format: Ctrl + shift + p

[<img src="https://i.imgur.com/pD2hUgX.png">](https://i.imgur.com/pD2hUgX.png)
