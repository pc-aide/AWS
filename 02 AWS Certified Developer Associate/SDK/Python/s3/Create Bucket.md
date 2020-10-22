# Create Bucket

## Demo 01
````python
import boto3

# Variables
REGION='ca-central-1'
# Only in lower case
BUCKET_NAME='demo-01-athena'

# Create an S3 client
s3_client = boto3.client('s3', region_name=REGION)
# Create bucket
response = s3_client.create_bucket(
  # Attributes bucket
  Bucket=BUCKET_NAME,
  # Contraint Region: outside us-east-1
  CreateBucketConfiguration={'LocationConstraint': REGION}
)
````
[<img src="https://i.imgur.com/b5YsX3p.png">](https://i.imgur.com/b5YsX3p.png)
