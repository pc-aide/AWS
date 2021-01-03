# 01 - Public

## Policy
````json
{
  "Version": "2012-10-17",
  "Id": "Policy1584325962077",
  "Statement": [
    {
      "Sid": "Stmt158432961082",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::bucketname.com/*"
    }
  ]
}
````
