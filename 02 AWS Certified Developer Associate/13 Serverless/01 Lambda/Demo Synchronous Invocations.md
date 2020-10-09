# Demo Synchronous Invocations

## Doc

## Acronym

## Intro
* Lambda\Test
* this sist is a synchronous invocation because we have been waiting for the execution result
* whick we find the "value1"

[<img src="https://i.imgur.com/NHBGQUT.png">](https://i.imgur.com/NHBGQUT.png)

* AWS cli:
````bash
aws lambda list-function --region us-east-1
````
[<img src="https://i.imgur.com/m4TuzLF.png">](https://i.imgur.com/m4TuzLF.png)

* invoke:
````bash
 aws lambda invoke --function-name Demo-Lambda \
 --cli-binary-format raw-in-base64-out \
 --payload '{"key1": "value1", "key2": "value2", "key3": "value3" }' \
 --region us-east-1 response.json
````
[<img src="https://i.imgur.com/QuGkup7.png">](https://i.imgur.com/QuGkup7.png)
