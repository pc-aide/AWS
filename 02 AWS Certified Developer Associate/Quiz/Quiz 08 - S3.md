# Quiz 08 - S3

## Questions
1) I tried creating an S3 bucket named "dev" but it didn't work. This is a new AWS Account and I have no buckets at all. What is the cause?
    * I'm missing IAM permissions to create a bucket
    * Bucket name must be globally unique & "dev" is already taken
* [Answer](https://i.imgur.com/FozARaA.png)
2) You've added files in your bucket and then enabled versioning. The files you've already added will have which version?
    * 1
    * 0
    * -1
    * null
* [Answer](https://i.imgur.com/HUKVBEl.png)
3) Your client wants to make sure the encryption is happening in S3, but wants to fully manage the encryption keys and never store them in AWS. You recommend
    * SSE-S3
    * SSE-KMS
    * SSE-C
    * Client Side Encryption
* [Answer](https://i.imgur.com/RpJrdNk.png)
4) Your company wants data to be encrypted in S3, and maintain control of the rotation policy for the encryption keys. You recommend
    * SSE-S3
    * SSE-KMS
    * SSE-C
    * Client Side Encryption
* [Answer](https://i.imgur.com/FngKXAs.png)
5) Your company does not trust S3 for encryption and wants it to happen on the application. You recommend
    * SSE-S3
    * SSE-KMS
    * SSE-C
    * Client Side Encryption
* [Answer](https://i.imgur.com/3prbGTZ.png)
6) The bucket policy allows our users to read/write files in the bucket, yet we were not able to perform a PutObject API call. What is your assessment?
    * The bucket policy is wrong
    * The IAM user has an explicit DENY in the attached IAM policy
    * You need to contact AWS Support to lift this limit
* [Answer](https://i.imgur.com/PNghHsM.png)
7) You have a website that loads files from another S3 bucket. When you try the URL of the files directly
   in your Chrome browser it works, but when the website you're visiting tries to load these files it doesn't. What's the problem?
    * The Bucket policy is wrong
    * The IAM policy is wrong
    * CORS is not enabled
    * Encryption is wrong
* [Answer](https://i.imgur.com/V7L8xSr.png)
8) Which encryption method requires HTTPS?
    * SSE-S3
    * SSE-KMS
    * SSE-C
    * Client Side Encryption
* [Answer](https://i.imgur.com/LgbOdaE.png)
