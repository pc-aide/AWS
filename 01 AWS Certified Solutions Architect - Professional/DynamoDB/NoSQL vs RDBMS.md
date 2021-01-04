# NoSQL vs RDBMS

## Acronym
* GSI - Global Secondary Indexe
* MS - Microsoft
* RDBMS - Relational DataBase Management System 

## Intro
* RDBMS (MS SQL or Oracle) 
  * flexible querying; expensive; does not scale well under high traffic
  * you design for **flexibility**
* NoSQL 
  * limited number of optimized query options; then slow & expensive
  * you design for the **specific**, limited nuber of queries, limited number of queries
* It's critical you know the business use cases (as **queries**) before design; maintain few tables

---

## NoSQL Design Best Practices
* Condiser data volume, shape, & volocity
* keep related data together
  * partition key & secondary indexes
* Use sort order
* Distribute queries
* Use GSIs
