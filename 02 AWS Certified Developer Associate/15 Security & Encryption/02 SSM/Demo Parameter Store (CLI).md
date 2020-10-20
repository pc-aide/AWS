# Demo Parameter Store (CLI)

## Acronym

## Doc

## Console
* System Manager\**Parameter Store**
    * Create parameter

[<img src="https://i.imgur.com/QXe8OJr.png">](https://i.imgur.com/QXe8OJr.png)
[<img src="https://i.imgur.com/o9bqTwN.png">](https://i.imgur.com/o9bqTwN.png)

* Name: /my-app/dev/db-url
* Description: Database URL
* Tier: Std (free) vs advanced ($$$)
* Type: String
* Value: dev.db.demo.com:3306
  * 3306:port
  
[<img src="https://i.imgur.com/T0b5eW4.png">](https://i.imgur.com/T0b5eW4.png)
[<img src="https://i.imgur.com/nNEaBQe.png">](https://i.imgur.com/nNEaBQe.png)
[<img src="https://i.imgur.com/RJzF15c.png">](https://i.imgur.com/RJzF15c.png)
[<img src="https://i.imgur.com/KU8zLnX.png">](https://i.imgur.com/KU8zLnX.png)

* Create another parameter
    * Name: /my-app/dev/db-password
    * Type: SecureString
    * KMS Key ID: alias/Demo-KMS
    * Value: ***
    
[<img src="https://i.imgur.com/DC8avxl.png">](https://i.imgur.com/DC8avxl.png)
[<img src="https://i.imgur.com/uVBypFE.png">](https://i.imgur.com/uVBypFE.png)
[<img src="https://i.imgur.com/0bGueJx.png">](https://i.imgur.com/0bGueJx.png)

* create another parameter store for prod
    * name: /my-app/prod/db-url
    * Type: String
    * Value: prod.db.demo.com:3306
    
[<img src="https://i.imgur.com/t1uzNJC.png">](https://i.imgur.com/t1uzNJC.png)

* last one parameter store (for pwd for prod)
    * name: /my-app/prod/db-password
    * Type: SecureString
    * KMS Key ID: Alias/Demo-KMS
    * Value: ***

[<img src="https://i.imgur.com/rlJReWC.png">](https://i.imgur.com/rlJReWC.png)

* we want to get access this parameter store with CLI
````bash
aws ssm get-parameters \
--names /my-app/dev/db-password /my-app/dev/db-url
````
[<img src="https://i.imgur.com/UoNyUHE.png">](https://i.imgur.com/UoNyUHE.png)

* to decrypt value pwd:
````bash
aws ssm get-parameters \
--names /my-app/dev/db-password /my-app/dev/db-url --with-decryption
````
[<img src="https://i.imgur.com/IHgj532.png">](https://i.imgur.com/IHgj532.png)

* parameters-by-path
````bash
aws ssm get-parameters-by-path \
--path /my-app/dev/
````
[<img src="https://i.imgur.com/ayApajd.png">](https://i.imgur.com/ayApajd.png

* recursive
````bash
aws ssm get-parameters-by-path \
--path /my-app/ --recursive
````
[<img src="https://i.imgur.com/oc6JoQh.png">](https://i.imgur.com/oc6JoQh.png)
