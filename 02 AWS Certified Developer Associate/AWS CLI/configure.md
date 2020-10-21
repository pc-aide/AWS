# configure

## Files
* .aws/{config,credentials}

[<img src="https://i.imgur.com/hozCF1n.png">](https://i.imgur.com/hozCF1n.png)

## First configure
1) Access Key ID
2) Secret Access Key
3) Default region
4) Default output
    * json
    * text
    * yaml
    
[<img src="https://i.imgur.com/Q3u2huI.png">](https://i.imgur.com/Q3u2huI.png)

### Test
````bash
# to test if my config working
aws s3 ls
````

[<img src="https://i.imgur.com/HydpeAj.png">](https://i.imgur.com/HydpeAj.png)

## Additon profile
* if we have many AWS account, just add "--profile String" whe configure
````bash
aws configure --profile dev
````

---

## get region
````bash
aws configure get region
````
[<img src="https://i.imgur.com/nD6GH8h.png">](https://i.imgur.com/nD6GH8h.png)
