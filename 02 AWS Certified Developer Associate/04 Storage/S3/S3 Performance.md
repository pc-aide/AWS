# S3 Performance

## Acronym
* KMS - Key Management Service
* SSE-KMS - Server side encryption

## Doc

## S3 - Baseline Performance
* S3 automatically scales to high request rates, latency 100-200 ms
* Your application can achieve at leat **3 500 PUT/COPY/POST/DELETE** & **5 500 GET/HEAD request per second** per prefix in a bucket
* There are no limits to the number of prefixes in a bucket
* <ins>Ex: (object path => prefix):</ins>
    * Bucket/folder1/sub1/file => /folder1/sub1/
    * Bucket/Folder2/sub2/file => /folder2/sub2/
    * Bukcet/1/file => /1/
    * Bucket/2/file => /2/
* If you spread reads across all four prefixes evenly, you can achieve 22k requests per second for GET & HEAD
    
### Diagram
[<img src="https://i.imgur.com/cQonKnG.png">](https://i.imgur.com/cQonKnG.png)

---

## S3 - KMS Limitation
* If your use SSE-KMS, you may be impacted by the KMS limits
* When you upload, it calls the **GenerateDataKey** KMS API
* When you download, it calls the **Decrypt** KMS API
* Count towards the KMS quota per second (**5 500, 10k, 30k req/s based on region)
* As of today, you cannot request a quota increase for KMS

### Diagram
[<img src="https://i.imgur.com/YSH3FBf.png">](https://i.imgur.com/YSH3FBf.png)

---

## S3 Performance
* Multi-Part upload
    * Recommended for files > 100MB, must use for files > 5GB
    * Can help parallelize uploads (speed up transfers)
* S3 Transfer Acceleration (upload only)
    * Increase transfer speed by transferring file to an AWS edge location which will forward the data to the S3 bucket 
      in the target region
    * Compatible with multi-part upload
    
### Diagram
* Multi-Part upload:

[<img src="https://i.imgur.com/LWt6eZJ.png">](https://i.imgur.com/LWt6eZJ.png)

* S3 Transfer Acceleration (upload only):

[<img src="https://i.imgur.com/4NJ0UOu.png">](https://i.imgur.com/4NJ0UOu.png)

---

## S3 Performance - S3 Byte-Range Fetches
* Parallelize GETs by requesting specific byte ranges
* Better resilience in case of failures
* <ins>#1 - Can be used to speed up downloads</ins>
* <ins>#2 - Can be used to retieve only partial data (for ex.: the head of a file)

### Diagram
* # 1:

[<img src="https://i.imgur.com/cn6WRAB.png">](https://i.imgur.com/cn6WRAB.png)

* # 2:

[<img src="https://i.imgur.com/lMLqeO3.png">](https://i.imgur.com/lMLqeO3.png)
