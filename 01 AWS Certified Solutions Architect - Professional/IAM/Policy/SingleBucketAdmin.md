# SingleBucketAdmin

## Policy
* Trusted entities: EC2
* Policy Name: SingleBucketAdmin
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Example",
      "Effect": "Allow",
      "Action": "*",
      "Resource": [
        "arn:aws:s3:::com.globo.demo.one",
        "arn:aws:s3:::com.globo.demo.one/*"
      ]
    }
  ]
}
````
* Role name: AllowSingleEC2BucketAccess
* Description: Allow instance to administer a single bucket

[<img src="https://i.imgur.com/9SP4xph.png">](https://i.imgur.com/9SP4xph.png)

---

## Test
* Launch instance\Configure Instance
  * IAM role: AllowSingleEC2BucketAccess
  
[<img src="https://i.imgur.com/lanZ4jK.png">](https://i.imgur.com/lanZ4jK.png)
[<igm src="https://i.imgur.com/SsAJMCx.png">](https://i.imgur.com/SsAJMCx.png)

* login ssh
  * list only s3://com.globo.demo.one
  
[<img src="https://i.imgur.com/IGalJlR.png">](https://i.imgur.com/IGalJlR.png)


---

## update policy
* if we update policy
  * e.g Resource: other bucket
  * bukcet-two :
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Example",
      "Effect": "Allow",
      "Action": "*",
      "Resource": [
        "arn:aws:s3:::com.globo.demo.two",
        "arn:aws:s3:::com.globo.demo.two/*"
      ]
    }
  ]
}
````
* try agin list our bukcet (aws cli)
* we will get an error
* but bucket 2 - it will work

[<img src="https://i.imgur.com/wv1DuPl.png">](https://i.imgur.com/wv1DuPl.png)
[<img src="https://i.imgur.com/QDgQU2J.png">](https://i.imgur.com/QDgQU2J.png)
