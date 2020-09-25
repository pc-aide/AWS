# AWS CLI STS Decode Errors

## Doc

## Acronym

## Intro
* When yur run API calls & they fail, you can get a long error message
* ex:
````text
# AWS CLI:
aws ec2 run-instances --dry-run --image-id ami-020caff809d5a5307 --instance-type t2.micro

# Error
An error occurred (UnauthorizedOperation) when calling the RunInstances operation: You are not authorized to perform this operation. Encoded authorization failure message: m-yNX1GWpvhAQbNfWjiqQrxo9wFerxnJD63lNghsGxQ-EnQltKQVzbXXJIRyUxJut33pczHMxrEmBJOSQwwYHf3xPfnFm1gIew6uLQCF8Hr-_j5uY4vGddQIIyGD7IntewAaxHpjQ16qAHmd2s9Q569wQazjNjS27miyr-z-XSkLDqwU7btVCJ6tWvgnIcQaUlcVdz1VpqJ6G-5DoXr93G3YNPrW1N-u5MmISKGM_yZhZ116QjggcLhCenjCR7eOhdTrEJ8anO6r5fov3CFEJmzrvGgqLPIUmWwX_sI1DsIwZ1rYjubcU_3ZJVK6SYxlV-jivtXutPt1O0xR05B-119iIX4-L-EDRZFNPEZbsHXHA5CD0JA5um2OVmy2M0_D13xWBC3_5tYTLE11dSTpz-cTnAQwTyFe-qk-BlWLRXuLNSzEzodZZKzqzN5KPjwvprGBd4CNmBBhybr-qFdFDCy6KX4tpKw-CPhL8XG67UUOz0wyJZzJjs3m2WPTgLko-vhr8VrdqW_I9S-jZM1REuzLNmf8vJzZEQ-smFTek-Xt_CWaQLvDX1DAqeyXObbeln0wpjaHNdauNx7V2Gk7sSzS0ky24S8TLlZ3dUbXMVVEV0q83afRHwg5IMuyLK9TcaQhXJe9gmDS6ZTZhzpq0d7YobcVW4ZThgv9xn4z5n5q_qnVKYUqSuAkEQ
````
