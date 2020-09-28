# S3 Replication (Cross Region & Same Region)

## Doc

## Acronym
* CRR - Cross Region Replication
* SRR - Same Region Replication

## S3 Replication (CRR & SRR)
* Must enable versioning in source & destination
* CRR
* SRR
* Buckets can be in different accounts
* Copying is asynchronous
* Must give proper IAM permissions to S3
* <ins>CRR - Use cases:</ins> compliance, lower latency access, replication across accounts
* <ins>SRR - Use cases:</ins> log aggreation, live replication between production & test accounts

### Diagram
[<img src="https://i.imgur.com/sKVaxBU.png">](https://i.imgur.com/sKVaxBU.png)

---

## S3 Replication - Notes
* After activating, only new objects are replicated (not retroactive)
* Fo DELETE operations:
    * If you delete without a version ID, it adds a delete marker, not replicated
    * If you delete wih a version ID, it deletes in the source, not replicated
* There is no "chaining" of replication
    * If bucket 1 has replication into bucket 2, which has replication into bucket 3
    * Then objects created in bucket 1 are not replicated to bucket 3
    
---

## Demo
