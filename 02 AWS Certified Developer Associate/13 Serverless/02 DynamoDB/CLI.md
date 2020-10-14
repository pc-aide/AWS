# CLI

## Acronym

## Terminology
* item = row

## Doc

## Intro
* --projection-expression: attributes to retrieve
* --filter-expression: filter results
* General CLI pagination options including DynamodB/S3
    * Optimization:
      * --page-size: full dataset is still received but each API call will request less data (help avoid
        timeouts)
    * Pagination:
      * --max-items: max number of results returned by the CLI. Returns NextToken
      * --starting-token: specify the last received NextToken to keep on reading
      
---

## Demo
* DynamoDB\UserPosts (table)
    * 3 items & 3 columns
    
    
[<img src="https://i.imgur.com/KVFNnLv.png">](https://i.imgur.com/KVFNnLv.png)

---

## AWS CLI
* projection-expression:
````bash
aws dynamodb scan \
--table-name UserPosts \
--projection-expression "user_id, content" \
--region us-east-1
````
[<img src="https://i.imgur.com/6V0OTFf.png">](https://i.imgur.com/6V0OTFf.png)

* filter-expression:
````bash
aws dynamodb scan --table-name UserPosts \
--filter-expression "user_id = :u" \
--expression-attribute-values '{ ":u": {"S":"2452usersoi3"}}' \
--region us-east-1
````
[<img src="https://i.imgur.com/ly2L9D9.png">](https://i.imgur.com/ly2L9D9.png)

* **page size**
* **1 API** call if you have 3 Items
````bash
aws dynamodb scan --table-name UserPosts \
--region us-east-1
````

* page file
* **4 API** calls if you have 3 Items
````bash
aws dynamodb scan --table-name UserPosts \
--page-size 1 \
--region us-east-1
````
[<img src="https://i.imgur.com/8Gt6Cv8.png">](https://i.imgur.com/8Gt6Cv8.png)

* max item:
    * **NextToken**
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

* count: 0
* ScannedCount: 0

[<img src="https://i.imgur.com/1CppfT7.png">](https://i.imgur.com/1CppfT7.png)
