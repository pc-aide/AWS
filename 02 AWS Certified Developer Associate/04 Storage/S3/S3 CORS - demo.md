# S3 CORS - demo

## Acronym

## Doc

## Intro
* Your Bucket web hosting:

[<img src="https://i.ibb.co/BNLG7Yh/image.png">](https://i.ibb.co/BNLG7Yh/image.png)
[<img src="https://i.ibb.co/H43WJg5/image.png">](https://i.ibb.co/H43WJg5/image.png)
[<img src="https://i.ibb.co/fdpDRhK/image.png">](https://i.ibb.co/fdpDRhK/image.png)
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

### Same Origin

* CORS demo (index.html):

````html<html>
  <head>
    <title>This is a test</title>
  </head>
  <body>
    <h1>Web site on my bucket</h1>
    <p>nothing from EC2</p>
  </body>
  
  <img src="cats.png" width=500/>
  
    <!-- CORS demo -->
    <div id="tofetch"/>
    <script>
        var tofetch = document.getElementById("tofetch");

        fetch('extra-page.html')
        .then((response) => { 
            return response.text();
        })
        .then((html) => {
            tofetch.innerHTML = html     
        });
    </script>
</html>
````

* extra-page.html
````html
<p> This <strong>extra page</strong> has been successfully loaded!</p>
````

[<img src="https://i.ibb.co/FVKcC11/image.png">](https://i.ibb.co/FVKcC11/image.png)

* Browser:

[<img src="https://i.imgur.com/clKQx1u.png">](https://i.imgur.com/clKQx1u.png)
[<img src="https://i.imgur.com/uxUErXh.png">](https://i.imgur.com/uxUErXh.png)

### other Origin
* Create a new bucket public + policy + ...

[<img src="https://i.imgur.com/6LLj1pe.png">](https://i.imgur.com/6LLj1pe.png)
[<img src="https://i.imgur.com/FOjszVv.png">](https://i.imgur.com/FOjszVv.png)
[<img src="https://i.imgur.com/nQQl0S5.png">](https://i.imgur.com/nQQl0S5.png)
[<img src="https://i.imgur.com/PIHiWYw.png">](https://i.imgur.com/PIHiWYw.png)
[<img src="https://i.imgur.com/WZ8dm6N.png">](https://i.imgur.com/WZ8dm6N.png)

* Delete extra-page from main bucket website :

[<img src="https://i.imgur.com/2prMl4Z.png">](https://i.imgur.com/2prMl4Z.png)

* Edit/update: index.html 
* juste need change in **fetch('url_other_bucket')**
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
    <div id="tofetch"/>
    <script>
        var tofetch = document.getElementById("tofetch");

        fetch('http://db-ca-central.s3-website.ca-central-1.amazonaws.com/extra-page.html')
        .then((response) => { 
            return response.text();
        })
        .then((html) => {
            tofetch.innerHTML = html     
        });
    </script>
</html>
````

[<img src="https://i.imgur.com/56TnAY8.png">](https://i.imgur.com/56TnAY8.png)

* Browser:

[<img src="https://i.imgur.com/RuqlHSh.png">](https://i.imgur.com/RuqlHSh.png)

* messages
````text
Access to fetch at 'http://db-ca-central.s3-website.ca-central-1.amazonaws.com/extra-page.html' from origin 'http://s3-ca-website.s3-website.ca-central-1.amazonaws.com' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource. If an opaque response serves your needs, set the request's mode to 'no-cors' to fetch the resource with CORS disabled.
````
````text
GET http://db-ca-central.s3-website.ca-central-1.amazonaws.com/extra-page.html net::ERR_FAILED
````
````text
(index):1 Uncaught (in promise) TypeError: Failed to fetch
````

* Need change CORS for second Bucket (db) from the origin

````xml
<CORSConfiguration>
	<CORSRule>
		<AllowedOrigin>http://s3-ca-website.s3-website.ca-central-1.amazonaws.com</AllowedOrigin>
		<AllowedMethod>GET</AllowedMethod>
		<MaxAgeSeconds>3000</MaxAgeSeconds>
		<AllowedHeader>Authorization</AllowedHeader>
	</CORSRule>
</CORSConfiguration>
````

* Browser

[<img src="https://i.imgur.com/KPs6aJN.png">](https://i.imgur.com/KPs6aJN.png)
[<img src="https://i.imgur.com/UDCqeFg.png">](https://i.imgur.com/UDCqeFg.png)
[<img src="https://i.imgur.com/wkML06Q.png">](https://i.imgur.com/wkML06Q.png)
[<img src="https://i.imgur.com/qN9GPgS.png">](https://i.imgur.com/qN9GPgS.png)
[<img src="https://i.imgur.com/1musTNr.png">](https://i.imgur.com/1musTNr.png)
[<img src="https://i.imgur.com/dQOy5Kz.png">](https://i.imgur.com/dQOy5Kz.png)
