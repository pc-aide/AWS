# S3 Pre-signed URLs

## Doc

## Acronym

## Intro
* Can generate pre-digned URLs using SDK or CLI
    * For downloads (easy, can use the CLI)
    * For uploads (harder, must use the SDK)
* Valid for a default of 3600 seconds, can change timeout with --expires-in[TIME_BY_SECONDS] argument
* Users given a pre-signed URL inherit the permissions of the person who generated the URL for GET / PUT
* Examples:
    * Allow only logged-in users to download a premium video on your S3 bucket
    * Allow an ever changing list of users to download files by generating URLs dynamically
    * Allow temporarily a user to upload a file to a precise location in our bucket
    
---

## Demo
````bash
aws s3 mb s3://demo-01-monitored
aws s3 cp beach.jpeg s3://demo-01-monitored
````
[<img src="https://i.imgur.com/FTzoc4b.png">](https://i.imgur.com/FTzoc4b.png)

* if try link this picture
* AccessDenied

[<img src="https://i.imgur.com/aXp79Sn.png">](https://i.imgur.com/aXp79Sn.png)
[<img src="https://i.imgur.com/wUjqUVa.png">](https://i.imgur.com/wUjqUVa.png)

* Try it on aws cli
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
