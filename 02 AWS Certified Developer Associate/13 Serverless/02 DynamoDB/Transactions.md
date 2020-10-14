# Transactions

## Doc

## Acronym
* WCU - Write Capacity Units
* RCU - Read Capacity Units
* ts - timestamp (epoch time)

## Intro
* **New feature** from November 2018
* Transaction = Ability to Create/Update/Delete multiple rows in different tables at the same time
* It's an "all or nothing" type of operation
* Write Modes: Standard, Transactional
* Read Modes: Eventual Consistency, Strong Consistency, Transactional
* Consume 2x of WCU/RCU

### Transactions
* AccountBalance Table:

| Account_id | balance | Last_transaction_ts |
|------------|---------|---------------------|
| Acct_21    | 230     | 1562503085          |
| Acct_45    | 120     | 1562503085          |

* BankTransactions Table:

| Transaction_id | Transaction_time | From_account_id | From_account_id | value |
|----------------|------------------|-----------------|-----------------|-------|
| Tx_12345       | 1561483349       | Acct_45         | Acct_21         | 45    |
| Tx_23456       | 1562503085       | Acct_21         | Acct_45         | 100   |

* A transaction is a write to **both table**, or none
