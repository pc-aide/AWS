# WCU & RCU - Throughput

## Acronym
* WCU - Write Capacity Units
* RCU - Read Capacity Units

## Doc

## Provisioned Throughput
* Table must have provisoned read & write capacity units
* **RCU**: throughput for reads
* **WCU**: throughput for writes
* Option to setup auto-scaling of throughput to meet demand
* Throughput can be exceeded temporarily using "burst credit"
* If bust credit are empty, you'll get a "ProvisionedThroughputException"
* It's then advised to do an exponential back-off retry

---

## WCU
* One WCU represents one write per second for an item up to 1 KB in size
* If the items are larger than 1 KB, more WCU are consumed
* **Example 1**: we write 10 objects per seconds of 2 KB each
    * How many WCU?
    * We need 2*10 = 20 WCU
* **Example 2**: we write 6 objects per second of 4.5 KB each
    * how many WCU?
    * 6*4 = 24.5 WCU !?
    * **Solution**: we need 6*5 = 30 WCU (4.5 gets rounded to the upper KB)
* **Example 3**: we write 120 objects per minutes of 2 KB each
    * how many WCU?
    * We need (120/60) * 2 = 4 WCU

---

## Strongly Consisten Read vs Eventually Consistent Read
* **Eventually Consistent Read**: If we read just after write, it's possible we'll get unexpected response
  because of replication
* **Strongly Consisten Read**: If we read just after a write, we will get the correct data
* **By default**: DynamoDB uses Eventually Consistent Reads, but GetItem, Query & Scan provide a "ConsistenRead"
  parameter you can set to True

### Diagram
[<img src="https://i.imgur.com/T3qvwSI.png">](https://i.imgur.com/T3qvwSI.png)

---

## RCU
* One RCU represents one strongly consisten read per second, or two eventually consistent read 
  per seconds, for an item up to **4 KB** in size
* If the items are larger than 4 KB, more RCU are consumed
* **Example 1**: 10 strongly consistent reads per seconds of 4 KB each
    * how many RCU?
    * 10 RCU ! (10*(4 KB/4KB)) = 10 RCU
* Example 2**: 16 eventually consistent reads per seconds of 12 KB each
    * how many RCU?
    * (16/2)*(12/4) = 24 RCU !? - (16/2 because it's eventually consistent
* **Example 3**: 10 strongly consistent reads per seconds of 6 KB each
    * how many RCU?
    * We need 10 * 8 KB/4 = 20 RCU (we have to round up 6 KB to 8 KB)
    
---

## Partitions Internal
* Data is divided in partitions
* Partition keys go through a hashing algorithm to know to which partition they go to
* To compute the number of partitions:
    * By capacity: (TOTAL RCU / 3000) + (TOTAL WCU / 1000)
    * By size: Total / 10GB
    * Total partitions = CEILING(MAX(Capacity,Size))
* **WCU & RcU are spread evely between partitions**

---

## Throttling
* If we exceed our RCU or WCU, we get **ProvisionedThroughputExceededExceptions**
* Reasons:
    * Hot keys: one partition key is being read too many time (popular item for ex)
    * Hot partitions:
    * Very large items: remember RCU & WCU depends on size of items
* Solutions:
    * Exponential back-off when exception is encountered (already in SDK)
    * Distribute partition keys as much as possible
    * If RCU issue, we can use DynamoDB Accelerator (DAX)
