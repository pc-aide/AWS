# put-public-access-block

## Switch
* aws s3api put-public-access-block help

## Examples
### 01 Enabled (Block public acces)
````bash
# Boolean flag (cfg)
aws s3api put-public-access-block \
--bucket demo-cors-apigw \
--public-access-block-configuration  BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=true,RestrictPublicBuckets=true
````
[<img src="https://i.imgur.com/a5e1tFz.png">](https://i.imgur.com/a5e1tFz.png)
````bash
# no working never set it:
# NoSuchPublicAccessBlockConfiguration
aws s3api get-public-access-block \
--bukcet demo-cors-apigw
````
[<img src="https://i.imgur.com/iFhMifU.png">](https://i.imgur.com/iFhMifU.png)
