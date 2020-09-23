# Bucket policies

## Doc

## Terminology
* Wildcard ("*") - everything, all

## Acronym
* ARN: Amzon Resource Name

## URLs
* [AWS Policy Generator](http://awspolicygen.s3.amazonaws.com/policygen.html)

## Intro
* Go to AWS Policy Generator
* Type of Policy: Bucket
* Effect: Deny
* Principal: *
* Actions: PutObject
* ARN: arn:aws:s3:::s3-ca-website/* - means everything after this "root bucket" nothing can't put any object
* Add Conditions
    * Condition: Null
    * Key: s3:x-amz-server-side-encryption
    * value: true
* Add Statement

[<img src="https://i.imgur.com/vHZJ9a0.png">](https://i.imgur.com/vHZJ9a0.png)
[<img src="https://i.imgur.com/sQMvisP.png">](https://i.imgur.com/sQMvisP.png)

* Second statemenet:
    * idem but for add conditions
        * Condition: StringNotEquals
        * key: s3:x-amz-server-side-encryption
        * value: AES256
        
* Generator policy
````json
{
  "Id": "Policy1600873966303",
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1600873703749",
      "Action": [
        "s3:PutObject"
      ],
      "Effect": "Deny",
      "Resource": "arn:aws:s3:::s3-ca-website/*",
      "Condition": {
        "Null": {
          "s3:x-amz-server-side-encryption": "true"
        }
      },
      "Principal": "*"
    },
    {
      "Sid": "Stmt1600873917047",
      "Action": [
        "s3:PutObject"
      ],
      "Effect": "Deny",
      "Resource": "arn:aws:s3:::s3-ca-website/*",
      "Condition": {
        "StringNotEquals": {
          "s3:x-amz-server-side-encryption": "AES256"
        }
      },
      "Principal": "*"
    }
  ]
}
````

* paste this json into your bucket policy

[<img src="https://i.imgur.com/XCQO1zB.png">](https://i.imgur.com/XCQO1zB.png)

### Test
* Upload a file.png

[<img src="https://i.imgur.com/siiKtQD.png">](https://i.imgur.com/siiKtQD.png)

* I can't upload this file.png

[<img src="https://i.imgur.com/uVWafDe.png">](https://i.imgur.com/uVWafDe.png)

* Try again to upload the cat.png with encryption:

[<img src="https://i.imgur.com/xJXhrLp.png">](https://i.imgur.com/xJXhrLp.png)
[<img src="https://i.imgur.com/V9VxoB4.png">](https://i.imgur.com/V9VxoB4.png)

* if we try with another encryption method: kms so error:

[<img src="https://i.imgur.com/wiSk3Ed.png">](https://i.imgur.com/wiSk3Ed.png)
[<img src="https://i.imgur.com/G6hEom7.png">](https://i.imgur.com/G6hEom7.png)
[<img src="https://i.imgur.com/waS24Op.png">](https://i.imgur.com/waS24Op.png)

---

## Block public access (account settings)

[<img src="https://i.imgur.com/OhNLQYk.png">](https://i.imgur.com/OhNLQYk.png)
