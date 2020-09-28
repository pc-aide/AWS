# presing
* Generate a pre-signed URL for S3 object

## Switch
* aws s3 presign help

## Syntax
* presign \<S3Uri\> [--expires-in <value>] --region \<value\> [optional if setted a region in profile]
    * value: seconds


## Examples
### 001 - Presing
````bash
# Before presing, need generate signature
aws configure set default.s3.signature_version s3v4
````

````bash
# Now presing
aws s3 presing s3://demo-01-monitored/beach.jpeg --expires-in 300
````
[<img src="https://i.imgur.com/n24PKg4.png">](https://i.imgur.com/n24PKg4.png)
[<img src="https://i.imgur.com/kzzO7EU.png">](https://i.imgur.com/kzzO7EU.png)

* working if you change region
* expiration

[<img src="https://i.imgur.com/A3nHGTU.png">](https://i.imgur.com/A3nHGTU.png)

* try with region
````bash
aws s3 presign s3://demo-01-monitored/beach.jpeg --expires-in 300 --region ca-central-1
````
[<img src="https://i.imgur.com/bibEHiB.png">](https://i.imgur.com/bibEHiB.png)

* working - no matter where is your region (jp,germany, etc): 

[<img src="https://i.imgur.com/mJ47AR9.png">](https://i.imgur.com/mJ47AR9.png)
