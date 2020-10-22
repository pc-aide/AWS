# List Buckets

## 01 with 1 bucket
````python
import boto3

# Create s3 client
s3 = boto3.client('s3')

# Call s3 to list current bucket
response = s3.list_buckets()

# Get a list of all bucket names from the response
buckets = [bucket['Name'] for bucket in response['Buckets']] 

# Print out the bucket list
print("Bucket List: %s" % buckets)
````
[<img src="https://i.imgur.com/AR5Ey7E.png">](https://i.imgur.com/AR5Ey7E.png)

## 02 with multiple buckets
[<img src="https://i.imgur.com/PpdygDH.png">](https://i.imgur.com/PpdygDH.png)
