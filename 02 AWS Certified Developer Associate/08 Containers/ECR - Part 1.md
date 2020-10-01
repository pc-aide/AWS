# ECR - Part 1

## Acronym
* ECR - Elastic Container Registry
* IAM - Identity & access management

## Doc

## Intro
* So far we've been using Docker images from Docker Hub (public)
* ECR is a private Docker image repository
* Access is controlled through IAM (permission errors => policy)
* **AWS CLI v1 login** command (may be asked at the **exam**):
````bash
$(aws ecr get-login --no-include-email --region eu-west-1)
````
* **AWS CLI v2 loggin** command (newer, may also be asked at the exam -**pipe**):
````bash
aws ecr get-login-password \
  --region <region> \
  | docker login \
    --username aws \
    --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com
````
* Docker Push & Pull:
````docker
docker push <aws_account_id>.dkr.ecr.<region>.amazonaws.com/demo:latest
````
````docker
docker pull <aws_account_id>.dkr.ecr.<region>.amazonaws.com/demo:latest
````

---

## Demo
* ECR\Repositories:

[<img src="https://i.imgur.com/lOWA4q4.png">](https://i.imgur.com/lOWA4q4.png)

* Install docker on machine:
````bash
apt install -y docker.io
````
* check up version
````docker
# Windows 1809 & hyper-v enabled
docker --version
````
[<img src="https://i.imgur.com/TYzEj8I.png">](https://i.imgur.com/TYzEj8I.png)

* need open port 80
````powershell
test-netconnection -computername -port 80
````
[<img src="https://i.imgur.com/MQIBpCd.png">](https://i.imgur.com/MQIBpCd.png)

* docker off (windows):

[<img src="https://i.imgur.com/OaLDPI5.png">](https://i.imgur.com/OaLDPI5.png)

* docker running:

[<img src="https://i.imgur.com/VWcvw9d.png">](https://i.imgur.com/VWcvw9d.png)

* docker build our image:

1) DockerFile
````dokcerFile
FROM httpd:2.4

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    jq \
    && rm -r /var/lib/apt/list/*

COPY ./public-html/ /usr/local/apache2/htdocs/

ADD bootstrap.sh /bootstrap.sh

RUN chmod +x /bootstrap.sh

CMD ["/bootstrap.sh"]
````
[<img src="https://i.imgur.com/GwwFqRn.png">](https://i.imgur.com/GwwFqRn.png)

2) index.html
````html
<html>
    <h1>
        This is a test from custom Docker image
    </h1>
    <p>
        This image is running on <strong>ECS</strong>, here's some info about this container & task:
        
    </p>
</html>
````
[<img src="https://i.imgur.com/GwZMcrn.png">](https://i.imgur.com/GwZMcrn.png)

3) bootStrap.sh
````shell
#!/bin/sh
set -e

# Add container metadata to index.html
echo "<pre>" >> /usr/local/apache2/htdocs/index.html
curl $ECS_CONTAINER_METADATA_URI | jq '.' >> /usr/local/apache2/htdocs/index.html
echo "</pre>" >> /usr/local/apache2/htdocs/index.html

# Run httpd
httpd-foreground
````
[<img src="https://i.imgur.com/HSbNPQw.png">](https://i.imgur.com/HSbNPQw.png)

* ls 

[<img src="https://i.imgur.com/PNeVjEC.png">](https://i.imgur.com/PNeVjEC.png)

* docker commands:
````dokcer
docker build -t my-httpd-image .
````
[<img src="https://i.imgur.com/SbJMuZG.png">](https://i.imgur.com/SbJMuZG.png)

* ECS\Repositories (to push my new-image):

[<img src="https://i.imgur.com/G8PGYnb.png">](https://i.imgur.com/G8PGYnb.png)

* Creatte repository
    * Repository name: demo
    
[<img src="https://i.imgur.com/sBmQYGq.png">](https://i.imgur.com/sBmQYGq.png)
[<img src="https://i.imgur.com/bVWIaFz.png">](https://i.imgur.com/bVWIaFz.png)

* PreReq (windows)
* aws cli v2

[<img src="https://i.imgur.com/fDApg6Y.png">](https://i.imgur.com/fDApg6Y.png)

* module ecr Powershell
````powershell
install-module aws.tools.ecr
````
[<img src="https://i.imgur.com/Vx9hDyR.png">](https://i.imgur.com/Vx9hDyR.png)

* login ecr :

[<img src="https://i.imgur.com/n5T6PTH.png">](https://i.imgur.com/n5T6PTH.png)

* docker buld -t demo .

[<img src="https://i.imgur.com/h9lnhlp.png">](https://i.imgur.com/h9lnhlp.png)
[<img src="https://i.imgur.com/smSqIhq.png">](https://i.imgur.com/smSqIhq.png)
[<img src="https://i.imgur.com/T6JkJ5j.png">](https://i.imgur.com/T6JkJ5j.png)
[<img src="https://i.imgur.com/PK1jzlh.png">](https://i.imgur.com/PK1jzlh.png)
[<img src="https://i.imgur.com/BzUa2iu.png">](https://i.imgur.com/BzUa2iu.png)

* tag this demo:

[<img src="https://i.imgur.com/bvCSLFI.png">](https://i.imgur.com/bvCSLFI.png)

* push:

[<img src="https://i.imgur.com/D7YoKxk.png">](https://i.imgur.com/D7YoKxk.png)
[<img src="https://i.imgur.com/yhJefqc.png">](https://i.imgur.com/yhJefqc.png)

* ECR\repository\new image:

[<img src="https://i.imgur.com/FlQEMcz.png">](https://i.imgur.com/FlQEMcz.png)

* dokcer pull:

[<img src="https://i.imgur.com/BpBK7me.png">](https://i.imgur.com/BpBK7me.png)
