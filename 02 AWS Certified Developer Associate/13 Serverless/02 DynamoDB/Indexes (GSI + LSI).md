# Indexes (GSI + LSI)

## Doc

## Acronym
* LSI Local Secondary Index
* GSI - Global Secondary Index
* RCU - Read Capacity Units
* WCU - Write Capacity Unitis
* ts - timestamp

## LSI
* Alternate range key for your table, **local to the hash key**
* Up to five local secondary indexes per table
* The sort key consists of exectly one scalar attribute
* The attribute that you choose must be a scalar String, Number, or Binary
* **LSI must be defined at table creation time**

### Diagram
[<img src="https://i.imgur.com/F0pFvCX.png">](https://i.imgur.com/F0pFvCX.png)

* LSI:

[<img src="https://i.imgur.com/iamKSnz.png">](https://i.imgur.com/iamKSnz.png)

---

## GSI
* To speed up queries on non-key attributes, use a GSI
* GSI = partition key + optional sort key
* The index is a new "table" & we can project attributes on it
    * The partition key & sort key of the original table are always projected (KEYS_ONLY)
    * Can specify extra attributes to project (INCLUDE)
    * Can use all attributes from mai ntable (ALL)
* Must define RCU/WCU for the index
* **Possibility to add/modify GSI (not LSI)**

### Diagram
[<img src="https://i.imgur.com/5emxKge.png">](https://i.imgur.com/5emxKge.png)

---

## Indexes & Throttling
* GSI:
    * <ins>If the writes are throttled on the GSI, then the main table will be throttled</ins>
    * Even if the WCU on the main tables are fine
    * Choose your GSI partition key carefully
    * Assign your WCU capacity carefully
* LSI:
    * Uses the WCU & RCU of the main table
    * No special throttling considerations
    
---

## Demo
* Create table
    * Table name: UserGames
    * Primary key: user_id
    * CheckBox: sort key
        * game_id (Number)
    * UncheckBox: Use default settings
    * Secondary indexes\Add index
        * Primary key: user_id
        * CheckBox: sort key
            * game_ts 
        * CheckBox: Create as LSI
    * Remove provioned capacity
        * RCU & WCU = 1
* Create

[<img src="https://i.imgur.com/jryZkMr.png">](https://i.imgur.com/jryZkMr.png)
[<img src="https://i.imgur.com/G8FYTab.png">](https://i.imgur.com/G8FYTab.png)

* Add data (UserGames):
````item
user_id String: oiufshn45iuh
game_id Number: 1234
game_ts String: 2018-09-09T05:06:07Z
````
[<img src="https://i.imgur.com/5Td7Aqq.png">](https://i.imgur.com/5Td7Aqq.png)

* Indexes
    * Name
      * user_id-game_ts-index

[<img src="https://i.imgur.com/11MOAQc.png">](https://i.imgur.com/11MOAQc.png)

* Query:
    * [table]
    * [Index]
    
[<img src="https://i.imgur.com/DitMkFM.png">](https://i.imgur.com/DitMkFM.png)
[<img src="https://i.imgur.com/Ajfw3tC.png">](https://i.imgur.com/Ajfw3tC.png)

* if i create index, so it will be GSI

[<img src="https://i.imgur.com/0o5f79T.png">](https://i.imgur.com/0o5f79T.png)
