# 02 - Access only via CloudFront

## Acronym
* OAI - Origin Access Identity

## Policy
````json
{
  "Version": "2012-10-17",
  "Id": "Policy158425962077",
  "Statement": [
    {
      "Sid": "2",
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam:CloudFront Origin Access Identity E2ABTYGTE44SS"
      },
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::bucketname/*"
    }
  ]
}
````

### Test
* URL (Bucket)
  * 403 forbidden
  
* URL (CloudFront
  * 200 OK
