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

* Edit your code lambda:
````python
import json

def lambda_handler(event, context):
    # TODO implement
    return "This is Lambda version 1"
````

[<img src="https://i.imgur.com/KurjTmF.png">](https://i.imgur.com/KurjTmF.png)

* Qualifiers:


[<img src="https://i.imgur.com/L5uPqhx.png">](https://i.imgur.com/L5uPqhx.png)
[<img src="https://i.imgur.com/vGP6839.png">](https://i.imgur.com/vGP6839.png)

* Actions\Publish new version
      * publish

[<img src="https://i.imgur.com/PvK34iz.png">](https://i.imgur.com/PvK34iz.png)
[<img src="https://i.imgur.com/aPWiQW3.png">](https://i.imgur.com/aPWiQW3.png)

* I can't modify my code (V1):

[<img src="https://i.imgur.com/DSYkqfY.png">](https://i.imgur.com/DSYkqfY.png)

* Go to $LATEST
      * change return to v2
      * add env variable: 
         * key: FOO
         * value: BAR
* publish new version
* can't change env var too
         
[<img src="https://i.imgur.com/fpDzLoR.png">](https://i.imgur.com/fpDzLoR.png)
[<img src="https://i.imgur.com/JMLEghc.png">](https://i.imgur.com/JMLEghc.png)
[<img src="https://i.imgur.com/RPhAvQl.png">](https://i.imgur.com/RPhAvQl.png)
[<img src="https://i.imgur.com/H3tVcp8.png">](https://i.imgur.com/H3tVcp8.png)
[<img src="https://i.imgur.com/rCXdRgj.png">](https://i.imgur.com/rCXdRgj.png)

* Create alias
      * Name: DEV
      * Version $LATEST
Save
      
[<img src="https://i.imgur.com/UbijQHg.png">](https://i.imgur.com/UbijQHg.png)
[<img src="https://i.imgur.com/4tpyk6Y.png">](https://i.imgur.com/4tpyk6Y.png)
[<img src="https://i.imgur.com/i9xYlYe.png">](https://i.imgur.com/i9xYlYe.png)

* Create 2<sup>nd</sup> alias
      * Name: TEST
      * Version: 2
* Create 3 <sup>rd</sup> alias
      * Name: PROD
      * Version: 1
      
[<img src="https://i.imgur.com/96OBCVw.png">](https://i.imgur.com/96OBCVw.png)
[<img src="https://i.imgur.com/dXGfToD.png">](https://i.imgur.com/dXGfToD.png)

* Alias: PROD
* i want to upgrade my code to v1 to v2: but slowly
* Alias configuration
      * Edit
      * shift :
         * 10% -> v2 & 90% -> v1

[<img src="https://i.imgur.com/BksZYdT.png">](https://i.imgur.com/BksZYdT.png)
[<img src="https://i.imgur.com/fS7uYVA.png">](https://i.imgur.com/fS7uYVA.png)

* Test

[<img src="https://i.imgur.com/Jq4Gwqr.png">](https://i.imgur.com/Jq4Gwqr.png)
[<img src="https://i.imgur.com/gtxpvLm.png">](https://i.imgur.com/gtxpvLm.png)
