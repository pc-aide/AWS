# DynamoDB

## Swithc
* aws dynamodb help

## Examples
### 01 projection-expression
````bash
aws dynamodb scan \
--table-name UserPosts \
--projection-expression "user_id, content" \
--region us-east-1
````
[<img src="https://i.imgur.com/6V0OTFf.png">](https://i.imgur.com/6V0OTFf.png)

### 02 filter-expression
````bash
aws dynamodb scan --table-name UserPosts \
--filter-expression "user_id = :u" \
--expression-attribute-values '{ ":u": {"S":"2452usersoi3"}}' \
--region us-east-1
````
[<img src="https://i.imgur.com/ly2L9D9.png">](https://i.imgur.com/ly2L9D9.png)

### 03 (One API)
````bash
# 1 API call if you have 3 Items
aws dynamodb scan --table-name UserPosts \
--region us-east-1
````

### 04 (four API)
````bash
# 4 API calls if you have 3 items
aws dynamodb scan --table-name UserPosts \
--page-size 1 \
--region us-east-1
````
[<img src="https://i.imgur.com/8Gt6Cv8.png">](https://i.imgur.com/8Gt6Cv8.png)

### 05 Max Item
````bash
aws dynamodb scan --table-name UserPosts \
--max-item 1 \
--region us-east-1
````
[<img src="https://i.imgur.com/X5dLl0P.png">](https://i.imgur.com/X5dLl0P.png)

* starting-token:
````bash
aws dynamodb scan --table-name UserPosts \
--max-item 1 \
--starting-toke <NextToken> \
--region us-east-1
````
[<img src="https://i.imgur.com/WRpYYR7.png">](https://i.imgur.com/WRpYYR7.png)
