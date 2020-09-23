# S3 Websites

## Acronym

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
````index.html
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

````error.html
<h1> Error page - we got an error</h1>
````

[<img src="https://i.imgur.com/BLAWDnF.png">](https://i.imgur.com/BLAWDnF.png)

* Go to Properties\**Static website hosting**

[<img src="https://i.imgur.com/62MV9uS.png">](https://i.imgur.com/62MV9uS.png)

* Endpoint : URL website from our bucket

[<img src="https://i.imgur.com/Ve6OqIZ.png">](https://i.imgur.com/Ve6OqIZ.png)
