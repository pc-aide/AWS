# Basic APIs

## Acronym
* WCU - Write Capacity Units
* RCU - Read Capacity Units

## Terminology
* item = row

## Doc

## Writing Data
* **PutItem** - Write data to DynamoDB (create data or full replace)
    * Consumes WCU
* **UpdateItem** - Update data in DynamoDB (partial update of attributes)
    * Possibility to use Atomic Conters & increase them
* **Conditional Writes**:
    * Accept a write / update only if conditions are respected, otherwise reject
    * Helps with concurrent access to items
    * No performance impact

---

## Deleting Data
* **DeleteItem**
    * Delete an individual row
    * Ability to perform a conditional delete
* **DeleteTable**
    * Delete a whole table & all its items
    * much quicker deletion than calling DeleteItem on all items
    
---

## Batching Writes
* **BatchWriteItem**
    * Up to 25 **PutItem** & / or **DeleteItem** in one call
    * Up to 16 MB of data
    * Up to 400 KB of data per item
* Batching allows you to save in latency by reducing the number of API calls done against DynamoDB
* Operations are done in parallel for better efficiency
* It's possible for part of a batch to fail, in which case we have the try the failed items (using
  exponential back-off alogorithm)
  
--
  
## Reading Data
* **GetItem**:
    * Read based on Primary key
    * Primary Key = HASH or HASH-RANGE
    * Eventually consistent read by default
    * Option ot use strongly consistent reads (more RCU - might take longer)
    * **ProjectionExpression** can be specified to include only certain attributes
* **BatchGetItem**:
    * Up to 100 items
    * Up to 16 MB of data
    * Items are retrieved in parallel to minimize latency
    
---

## Query
* **Query** returns items based on:
    * PartitionKey value (**must be = operator**)
    * SortKey value (=, <, <=, >, >=, Between, Begin) - optional
    * FilterExpression to further filter (client side filtering)
* Returns:
    * Up to 1 MB of data
    * Or number of items specified in **Limit**
* Able to do pagination on the results
* Can query table, a local secondary index, or a global secondary index

---

## Scan
* **Scan** the entire table & then filter out data (inefficient)
