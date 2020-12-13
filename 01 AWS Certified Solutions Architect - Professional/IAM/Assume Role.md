# Assume Role

## IAM Groups
* Permissions:

[<img src="https://i.imgur.com/a7KxjIf.png">](https://i.imgur.com/a7KxjIf.png)

* Show Policy
````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "sta:AssuemeRole",
      "Resource": "arn:aws:iam::018116317022:role/allow-ec2-full-access"
    }
  ]
}
````

* Trust relationships:

[<img src="https://i.imgur.com/kRL2hXf.png">](https://i.imgur.com/kRL2hXf.png)

````json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": "arn:aws:iam::736420608985:root"
      },
      "Action": "sts:AssumeRole",
      "Condition": {}
    }
  ]
}
````

---


## Switch Role
[<img src="https://i.imgur.com/1daQz4K.png">](https://i.imgur.com/1daQz4K.png)

---

