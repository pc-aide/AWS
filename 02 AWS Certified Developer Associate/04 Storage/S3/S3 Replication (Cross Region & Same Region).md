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
````bash
aws s3 mb s3://demo-01-origin
aws s3 mb s3://demo-01-replica --region us-west-1
````
[<img src="https://i.imgur.com/L0df5gW.png">](https://i.imgur.com/L0df5gW.png)

````bash
# upload file
aws s3 cp cat.jpg s3://demo-01-origin
# Versioning ON for 2x buckets
aws s3api put-bucket-versioning --bucket demo-01-origin --versioning-configuration Status=Enabled
aws s3api put-bucket-versioning --bucket demo-01-replica --versioning-configuration Status=Enabled
````

* Enabled replication on bucket-origin:

[<img src="https://i.imgur.com/O59P5OJ.png">](https://i.imgur.com/O59P5OJ.png)

* Replication rule:

[<img src="https://i.imgur.com/ZqORVkG.png">](https://i.imgur.com/ZqORVkG.png)
[<img src="https://i.imgur.com/RXYo7kE.png">](https://i.imgur.com/RXYo7kE.png)

* IMA Role & Rule name:

[<img src="https://i.imgur.com/CdevgpW.png">](https://i.imgur.com/CdevgpW.png)
[<img src="https://i.imgur.com/A461mrB.png">](https://i.imgur.com/A461mrB.png)
[<img src="https://i.imgur.com/vnVPpxS.png">](https://i.imgur.com/vnVPpxS.png)

* Resume between 2x buckets:
* CRR: 

[<img src="https://i.imgur.com/MZvuLZ6.png">](https://i.imgur.com/MZvuLZ6.png)
[<img src="https://i.imgur.com/4m7OpHM.png">](https://i.imgur.com/4m7OpHM.png)

* New IAM Role:

[<img src="https://i.imgur.com/RQ2KJdY.png">](https://i.imgur.com/RQ2KJdY.png)

* So nothing in Replica:

[<img src="https://i.imgur.com/HzZw33S.png">](https://i.imgur.com/HzZw33S.png)

* Upload a new file (with Replication enabled):

````bash
aws s3 cp mini_colley.jpg s3://demo-01-origin
````
[<img src="https://i.imgur.com/UP5cxxH.png">](https://i.imgur.com/UP5cxxH.png)
[<img src="https://i.imgur.com/SYRSB7i.png">](https://i.imgur.com/SYRSB7i.png)
[<img src="https://i.imgur.com/PYrtSS1.png">](https://i.imgur.com/PYrtSS1.png)

````bash
# upload another file
aws s3 cp beach.jpeg s3://demo-01-origin
````
[<img src="https://i.imgur.com/ZM8fCij.png">](https://i.imgur.com/ZM8fCij.png)

* Try to delete beach on origin bucket
````bash
aws s3 rm s3://demo-01-origin/beach.jpeg
````
[<img src="https://i.imgur.com/uFmEpRX.png">](https://i.imgur.com/uFmEpRX.png)
[<img src="https://i.imgur.com/WjqHAtZ.png">](https://i.imgur.com/WjqHAtZ.png)
[<img src="https://i.imgur.com/ZHQStne.png">](https://i.imgur.com/ZHQStne.png)
