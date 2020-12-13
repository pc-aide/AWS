# Bucket Policy

## E.g 01 - List + Get (one Bucket)
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
