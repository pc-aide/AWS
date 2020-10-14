# Operations

## Acronym
* RCU - Read Capacity Units
* WCU - Write Capacity Units
* EMR - Elastic MapReduce (Managed Hadoop Framework)

## Doc

## Intro
* **Table Cleanup**:
    * Option 1: Scan + Delete => very slow, expensive, consumes RCU & WCU
    * Option 2: **Drop Table** + Recreate table => fast, cheap, efficient
* **Copying a DynamoDB Table**:
    * Option 1: Use AWS DataPipeline (uses EMR)
    * Option 2: Create a backup & restore the backup into a new table name (can take some time)
    * Option 3: Scan + Write => write own code
    
### Diagram
[<img src="https://i.imgur.com/uEwRUnG.png">](https://i.imgur.com/uEwRUnG.png)
