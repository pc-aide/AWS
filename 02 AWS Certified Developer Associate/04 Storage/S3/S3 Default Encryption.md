# S3 Default Encryption

## Acronym

## Doc

## Intro
* The old way to enable default encryption was to use a bucket policy & refuse any HTTP command without the proper headers
````json
{
  "version": "2012-10-17",
  "Id": "PutObjPolicy",
  "Statement": [
    "Sid": "DenyIncorrectEncryptionHeader",
    "Effect": "Deny",
    "Principal": "*",
    "Action": "s3-PutObject",
    "Resources": "arn:aws:s3:::\<bucketName\>/*",
    "Condition": {
      "StringNotEquals": {
        "s3:x-amz-server-side-encryption": "AES256"
      }
    }
  ]
}
````

````json
{
  "Sid": "DenyUnEncryptionObjectUploads",
  "Effect": "Deny",
  "Principal": "*",
  "Action": "s3:PutObject",
  "Resource": "arn:aws:s3:::\<BucketName\>/*",
  "Condition": {
    "Null": {
      "s3:x-amz-server-side-encryption": true
    }
  }
}
````
* Tne new way is to use "default encryption" option in S3
* Note: Bucket Policies are evaluated before "default encryption"

### Demo
* Defualt encryption\AES-256:

[<img src="https://i.imgur.com/tyMTuep.png">](https://i.imgur.com/tyMTuep.png)

* Upload a file.png:

[<img src="https://i.imgur.com/4agHYwV.png">](https://i.imgur.com/4agHYwV.png)

* Encryptin: AES256:

[<img src="https://i.imgur.com/FwtNr8O.png">](https://i.imgur.com/FwtNr8O.png)

* Overview:

[<img src="https://i.imgur.com/Pp0x3sp.png">](https://i.imgur.com/Pp0x3sp.png)
[<img src="https://i.imgur.com/cZX3Gws.png">](https://i.imgur.com/cZX3Gws.png)
