# Bucket Policy

## E.g 01 - List + Get (one Bucket)
* if we remove Ln 18 & Ln20 (GetObject + bucketname/*), the user can't now **download** from this bucket:

[<img src="https://i.imgur.com/frjRzvh.png">](https://i.imgur.com/frjRzvh.png)
  
  
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::736420608985:root"
      },
      "Action": [
        "s3:ListBucket",
        "s3:GetObject"
      ],
      "Resource": [
        "arn:aws:s3:::bucketname",
        "arn:aws:s3:::bucketname/*"

      ]
    }
  ]
}
````
