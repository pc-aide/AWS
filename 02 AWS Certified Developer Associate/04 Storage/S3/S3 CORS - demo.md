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
* Create a new bucket public + policy 

[<img src="https://i.imgur.com/6LLj1pe.png">](https://i.imgur.com/6LLj1pe.png)
[<img src="https://i.imgur.com/FOjszVv.png">](https://i.imgur.com/FOjszVv.png)
[<img src="https://i.imgur.com/nQQl0S5.png">](https://i.imgur.com/nQQl0S5.png)
