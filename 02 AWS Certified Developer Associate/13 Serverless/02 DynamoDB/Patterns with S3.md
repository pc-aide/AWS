# Patterns with S3

## Acronym

## Doc

## Large Objects Pattern
* small metadata
  * ex
    * name
    * size
    * location S3
    * etc
* large data to S3
  * ex
    * 3 GB
    
### Diagram
[<img src="https://i.imgur.com/nXV28ip.png">](https://i.imgur.com/nXV28ip.png)

---

## Indexing S3 objects metadata
* Writes -> S3 -> Lambda Funcition (invoked) -> DynamoDB Table
    * DynamoDB table:
      * API for object metadata:
          * Search by data
          * Total storage used by a customer
          * List of all objects with certain attributes
          * Find all objects uploaded within a date range
          
### Diagram
[<img src="https://i.imgur.com/rgEwLRa.png">](https://i.imgur.com/rgEwLRa.png)
