# S3 CORS

## Acronym
* CORS - Cross-Origin Resource Sharing

## Doc

## Intro
* An **origin** is a scheme (protocol), host (domain) & port
    * E.g.: <ins>https://www.example</ins> (implied port is 443 for HTTPS, 80 for HTTP)
* CORS means Cross-Origin Resource Sharing
* **Web Browser** based mechanism to allow requests to other origins while visiting the main origin
* Same origing: <ins>**http://example.com**/app1</ins> & <ins>**http://example.com**/app2</ins>
* Different origins: <ins>http://www.example.com</ins> & <ins>http://other.example.com</ins>
* The requests won't be fulfilled unless the other origin allows for the requests, using **CORS Headers (ex: Access-Control-Allow-Origin)**


### Diagram
* What is an Origin?

[<img src="https://i.imgur.com/o1HAPRR.png">](https://i.imgur.com/o1HAPRR.png)


* Comparaison between browser (client) & ex: db
* Access controll allow origin

[<img src="https://i.imgur.com/u2QAYIP.png">](https://i.imgur.com/u2QAYIP.png)

* Wildcard

[<img src="https://i.imgur.com/VNEVuC2.png">](https://i.imgur.com/VNEVuC2.png)

* Broswer:

[<img src="https://i.imgur.com/AmYaUzp.png">](https://i.imgur.com/AmYaUzp.png)

---

## S3 CORS
* If a client does a cross-oring request on our **S3** bucket, we need to eneable the correct **CORS headers**
* You can allow for a specific origin or for * (all origins)

### Diagram
[<img src="https://i.imgur.com/JQ9zSm7.png">](https://i.imgur.com/JQ9zSm7.png)
