# AWS Signature v4 Signing

## Acronym
* S3 - Simple Storage Service

## Doc

## Intro
* When you call the AWS HTTP API, you sign the request so that AWS can identify you, using your AWS credentials (access key & secret key)
* Note: some requests to Amazon S3 don't need to be signed
* If you use the SDK or CLI, the HTTP requests are signed for you
* You should sign an AWS HTTP request using Singnature v4 (SigV4)

### Diagram
[<img src="https://i.imgur.com/GJG2jPB.png">](https://i.imgur.com/GJG2jPB.png)

---

## SigV4 Request examples
* HTTP Header option:

[<img src"https://i.imgur.com/gcB8lAn.png">](https://i.imgur.com/gcB8lAn.png)

* Query String option (ex: S3 pre-signed URLs):

[<img src="https://i.imgur.com/1vFSvOQ.png">](https://i.imgur.com/1vFSvOQ.png)

### Demo
* open file.png (S3)
    * response
    * X-Amz-Singature
    * Amz-Credential
    * Amz-Security-Token
    
[<img src="https://i.imgur.com/1quyssa.png">](https://i.imgur.com/1quyssa.png)
