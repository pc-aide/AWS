# Configure

## swith
* list
* profile
    * Multiple account AWS CLI

## Acronym
* IAM - Identity & access management

### Intro
* Don't share your AWS Access key & Secret key with anyone!

---

### Diagram
[<img src="https://i.imgur.com/r9hLf3t.png">](https://i.imgur.com/r9hLf3t.png)

---

### Configure
* Access key & Secret key to get it from IAM
````bash
aws configure
````
[<img src="https://i.imgur.com/aITqGcC.png">](https://i.imgur.com/aITqGcC.png)

---

### files
* /home/ubuntu/.aws/{config,credentials}

---

### list
````bash
aws configure list
````
[<img src="https://i.imgur.com/IxQZsea.png">](https://i.imgur.com/IxQZsea.png)

---

### profile
````bash
aws configure --profile \<String\>
````

#### mfa (session temporary)
````bash
aws configure --profile mfa
````

[<img src="https://i.imgur.com/X49fVAJ.png">](https://i.imgur.com/X49fVAJ.png)

````bash
# add this line for mfa
aws_session_token = ...
````

[<img src="https://i.imgur.com/YBrYQJL.png">](https://i.imgur.com/YBrYQJL.png)
