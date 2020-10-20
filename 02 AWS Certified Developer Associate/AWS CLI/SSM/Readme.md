# SSM

## SWitchs
* aws ssm help

## Syntax
* get-parameters --names <value>
* get-parameters-by-path --path <value>

## Examples
### 01 get-parameters
````bash
aws ssm get-parameters \
--names /my-app/dev/db-password /my-app/dev/db-url
````
[<img src="https://i.imgur.com/UoNyUHE.png">](https://i.imgur.com/UoNyUHE.png)

### 02 path
````bash
aws ssm get-parameters-by-path \
--path /my-app/dev/
````
[<img src="https://i.imgur.com/ayApajd.png">](https://i.imgur.com/ayApajd.png
