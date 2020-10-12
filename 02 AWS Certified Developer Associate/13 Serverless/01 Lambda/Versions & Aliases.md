# Versions & Aliases

## Doc

## Acronym
* ARN - Amazon Resource Name

## Lambda Version
* When you work on a Lambda function, we work on **$LATEST**
* When we're ready to publish a Lambda function, we create a version
* Version are **immuatble**
    * no change - we can't change the code
* Versions have increasing version numbers
* Versions get their own ARN
* Version = code + configuration (nothing can be changed - immutable)
* Each version of the lambda function can be accessed

### Diagram
[<img src="https://i.imgur.com/OIZPo0d.png">](https://i.imgur.com/OIZPo0d.png)

---

## Aliases
* Aliases are "**pointers**" to Lambda function versions
* We can define a "dev", "test", "prod" aliases & have them point at different lambda versions
* Aliases are mutable
* Aliases enable Blue/Green deployment by assigning weight to lambda functions
* Aliases enable stable configuration of our event triggers/destinations
* Aliases have their own ARNs
* **Aliases can't reference aliases**

### Diagram
[<img src="https://i.imgur.com/NSCGh2L.png">](https://i.imgur.com/NSCGh2L.png)

---

## Demo
* Create new function
    * Option: Author from scratch
    * Function name: Lambda-Version-Demo
    * Runtime: Python
    
[<img src="https://i.imgur.com/5AcayEE.png">](https://i.imgur.com/5AcayEE.png)
