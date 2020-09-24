# S3 Websites

## Acronym

## URLs
* [AWS Policy Generator](https://awspolicygen.s3.amazonaws.com/policygen.html)

## Doc

## Intro
* S3 can host **static** websites & have them accessbile on the www
* The website URL will be:
    * \<bucket-name\>.s3-website**-**\<AWS-region\>.amazonaws.com
    * or
    * \<bucket-name\>.s3-website**.**\<AWS-region\>.amazonaws.com
* If you get a 403 (Forbidden) error, make sure the bucket policy allows public reads!

---

## Demo
* upload this 2x files
	* index.html
	* error.html
````html
<html>
  <head>
    <title>This is a test</title>
  </head>
  <body>
    <h1>Web site on my bucket</h1>
    <p>nothing from EC2</p>
  </body>
  
  <img src="cats.png" width=500/>
  
  <!-- CORS demo -->
  <!-- <div id="tofetch"/>
  <scrip>
	var tofetch = document.getElementByID="tofetch");

	fetch('http://stephane-cors-other.s3-website-eu-west-1.amazonaws.com/extra-page.html')
	.then((response) => {
		return response.text();
	})
	.then((html) => {
		tofetch.innerHTML = html
	});
  </script -->
</html>
````

````html
<h1> Error page - we got an error</h1>
````

[<img src="https://i.imgur.com/BLAWDnF.png">](https://i.imgur.com/BLAWDnF.png)

* Go to Properties\**Static website hosting**

[<img src="https://i.imgur.com/62MV9uS.png">](https://i.imgur.com/62MV9uS.png)

* Endpoint : URL website from our bucket

[<img src="https://i.imgur.com/Ve6OqIZ.png">](https://i.imgur.com/Ve6OqIZ.png)

## Browser
* error - 403 Forbidden

[<img src="https://i.imgur.com/0WGD6Jv.png">](https://i.imgur.com/0WGD6Jv.png)

### Solution
* Step 01: Block pubic access -> off -> on

[<img src="https://i.imgur.com/ZPI5OMM.png">](https://i.imgur.com/ZPI5OMM.png)
[<img src="https://i.imgur.com/jqMEWhY.png">](https://i.imgur.com/jqMEWhY.png)
[<img src="https://i.imgur.com/TwFM4zs.png">](https://i.imgur.com/TwFM4zs.png)

* Step 02: Bluck policy:
* Go to AWS Policy Generator

* type: S3
* Effect: Allow
* Principal: *
* Actions: GetObject
* ARN: arn:aws:s3:::s3-ca-website/*
* Add statement
* Generator policy
````json
{
  "Id": "Policy1600971218935",
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "Stmt1600971198847",
      "Action": [
        "s3:GetObject"
      ],
      "Effect": "Allow",
      "Resource": "arn:aws:s3:::s3-ca-website/*",
      "Principal": "*"
    }
  ]
}
````

[<img src="https://i.imgur.com/7FQaRSA.png">](https://i.imgur.com/7FQaRSA.png)
[<img src="https://i.imgur.com/9H34xVG.png">](https://i.imgur.com/9H34xVG.png)
[<img src="https://i.imgur.com/jfxbaHj.png">](https://i.imgur.com/jfxbaHj.png)
[<img src="https://i.imgur.com/X6TonSf.png">](https://i.imgur.com/X6TonSf.png)
[<img src="https://i.imgur.com/ozgALOF.png">](https://i.imgur.com/ozgALOF.png)
