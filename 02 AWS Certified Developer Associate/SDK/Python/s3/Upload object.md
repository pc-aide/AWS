# Upload object

## 01 uload one file
````python
import boto3

# Create s3 client
s3 = boto3.client('s3')

# file from touch file.txt
FileName = 'file.txt'
BucketName = 'demo-01-python'

# Upload & automatic parts in parallel (if file > 5GB, so split in 100MB)
s3.upload_file(FileName,BucketName,FileName)
````
[<img src="https://i.imgur.com/z7iIBzc.png">](https://i.imgur.com/z7iIBzc.png)
[<img src="https://i.imgur.com/pGlzYxN.png">](https://i.imgur.com/pGlzYxN.png)
