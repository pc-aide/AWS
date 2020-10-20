# Quiz 25 - Security & Encryption

## Questions
1. To enable encryption in flight, we need to have
    * an HTTP endpoint with a SSL certificate
    * an HTTPS endpoint with a SSL certificate
    * a TCP endpoint
* [Answer](https://i.imgur.com/vavJde5.png)
2. Server side encryption means that the data is sent encrypted to the server first
    * true
    * false
* [Answer](https://i.imgur.com/MMdJpDr.png)
3. In server side encryption, only the encryption happens on the server. Where does the decryption happen?
    * The Server
    * The Client
* [Answer](https://i.imgur.com/vxIlyQz.png)
4. In client side encryption, the server must know our encryption scheme to accept the data
    * true
    * false
* [Answer](https://i.imgur.com/vDwXzc7.png)
5. We need to create User Keys in KMS before using the encryption features for EBS, S3, etc...
    * true
    * false
* [Answer](https://i.imgur.com/HYuLhBt.png)
6. We'd like to encrypt 400 KB of data. We should use
    * AWS KMS Encrypt call
    * AWS KMS GenerateDataKey call & encrypt client side
* [Answer](https://i.imgur.com/NAMlKRN.png)
7. We'd like our Lambda function to have access to a database password. We should
    * Embed it in the code
    * Have it as a plaintext environment variable
    * Have it as an encrypted environment variable & decrypt it at runtime
* [Answer](https://i.imgur.com/RGZAgEU.png)
8. We would like to audit the values of an encryption value over time
    * We should use AWS KMS versioning feature
    * We should use S3
    * We should use SSM Parameter Store
* [Answer](https://i.imgur.com/eUPvHUq.png)
9. An EC2 instance is trying to download a file from S3 that is encrypted with SSE:KMS. It's getting a denied exception, even though the IAM policy allows access to that S3 object. What do you recommend?
    * Add an S3 bucket policy
    * Add permission for KMS:Decrypt
    * Add permision for KMS:Encrypt
    * Add permission for S3:Decrypt
* [Answer](https://i.imgur.com/fmsvpOk.png)
10. You would like to store secrets and have automatic rotation. What's your recommendation?
    * Secrets Manager
    * Parameter Store with KMS & Parameter Policy
    * SSE-S3 with lifecycle policies
    * DynamoDB with KMS
* [Answer](https://i.imgur.com/JygGnbk.png)
11. How to encrypt existing CloudWatch Logs?
    * Do it through the console
    * Encrypt with them with the **associate-kms-key** API call
    * Encrypt with them with the **create-log-group** API call
    * Encrypt with them with the **update-log-group** API call
* [Answer](https://i.imgur.com/HL0dtWe.png)
