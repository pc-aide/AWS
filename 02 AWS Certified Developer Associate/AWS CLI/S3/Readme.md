# S3

## Switch
* aws s3 help

## Examples
### 00 list all buckets
````bash
aws s3 ls
````
[<img src="https://i.imgur.com/CzGw12h.png">](https://i.imgur.com/CzGw12h.png)

### 01 create bucket
````bash
aws s3 s3://demo-01-events-lambda --region us-east-1
````
[<img src="https://i.imgur.com/47TVkeZ.png">](https://i.imgur.com/47TVkeZ.png)

### 02 upload file
````bash
aws s3 cp <file> s3://<bucketName>
````
[<img src="https://i.imgur.com/E3UKkmy.png">](https://i.imgur.com/E3UKkmy.png)

### 03 encryption file
