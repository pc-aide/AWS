# Demo - Firehose - Intro

## Acronym
* IAM - Identity & Access Management
* O/P - OutPut
* SSE - Server-Side Encryption

## Console
* Kinesis\Kinesis Data Firehose\Create delivery stream
  * Delivery stream name: DemoFirehose
  * Source
    * RadioButton
      * Direct PUT or other sources
      * Kinesis Data Stream
  * SSE
    * CheckBox
      * Enable SSE for source refords in delivery stream

[<img src="https://i.imgur.com/H4VzCUk.png">](https://i.imgur.com/H4VzCUk.png)
[<img src="https://i.imgur.com/I1gNODf.png">](https://i.imgur.com/I1gNODf.png)
[<img src="https://i.imgur.com/YzCQP3r.png">](https://i.imgur.com/YzCQP3r.png)

* Process records
  * Data transformation
    * RadioButton
      * Disabled
      * Enabled
  * Convert record format
    * RadioButton
      * Disabled
      * Enabled
  
[<img src="https://i.imgur.com/A3ImcTY.png">](https://i.imgur.com/A3ImcTY.png)
[<img src="https://i.imgur.com/MPN6rg3.png">](https://i.imgur.com/MPN6rg3.png)

* Choose a destination
  * Destination
    * RadioButton
      * Amazon S3
      * Amazon Redshift
      * Amazon ElasticSearch
      * HTTP Endpoint
      * Third-party service provider
  * S3 destination
    * S3 bucket: demo-01-kineis-firehosw
    * S3 prefix 
      * default: YYYY/MM/dd/HH (UTC)
    * S3 error prefix
      
[<img src="https://i.imgur.com/gPIkORk.png">](https://i.imgur.com/gPIkORk.png)
[<img src="https://i.imgur.com/aVrKTL1.png">](https://i.imgur.com/aVrKTL1.png)

* Configure settings
  * S3 buffer conditions
    * Buffer size (MiB): 
    * Buffer interface (seconds):
  * S3 compression & encryption
    * S3 compression
      * RadioButton
        * Disabled
        * GZIP
        * Snappy
        * Zip
        * Hadoop-Campataible Snappy
    * S3 encryption
      * RadioButton
        * Disabled
        * Enabled
    * Error logging
      * RadioButton
        * Disabled
        * Enabled
    * Tags - optional
      * Key
      * Value - optional
    * Permmissions\IAM role
      * RadioButton
        * Create or update IAM role **KinesisFirehose-Demo**
        * Choose existing IAM role
      
    
[<img src="https://i.imgur.com/9pk5bR7.png">](https://i.imgur.com/9pk5bR7.png)
[<img src="https://i.imgur.com/JJUFd5s.png">](https://i.imgur.com/JJUFd5s.png)
[<img src="https://i.imgur.com/tUPkLlc.png">](https://i.imgur.com/tUPkLlc.png)
[<img src="https://i.imgur.com/1BqfLEI.png">](https://i.imgur.com/1BqfLEI.png)
[<img src="https://i.imgur.com/cCng5ae.png">](https://i.imgur.com/cCng5ae.png)

* O/P (demo)

[<img src="https://i.imgur.com/wnRmfH7.png">](https://i.imgur.com/wnRmfH7.png)
[<img src="https://i.imgur.com/3rMnoVU.png">](https://i.imgur.com/3rMnoVU.png)

* Test with demo data

[<img src="https://i.imgur.com/z750JSy.png">](https://i.imgur.com/z750JSy.png)
[<img src="https://i.imgur.com/oa7glkR.png">](https://i.imgur.com/oa7glkR.png)

* S3\Check up
  * new folder

[<img src="https://i.imgur.com/LGcXjQw.png">](https://i.imgur.com/LGcXjQw.png)
[<img src="https://i.imgur.com/2Jk4yap.png">](https://i.imgur.com/2Jk4yap.png)
[<img src="https://i.imgur.com/WhzMwxE.png">](https://i.imgur.com/WhzMwxE.png)
[<img src="https://i.imgur.com/VYggEqS.png">](https://i.imgur.com/VYggEqS.png)
[<img src="https://i.imgur.com/gbREC9d.png">](https://i.imgur.com/gbREC9d.png)

* Monitoring (Firehose)

[<img src="https://i.imgur.com/2OeAWyh.png">](https://i.imgur.com/2OeAWyh.png)

* Amazon S3 Logs\Log group
  * <path>
  
[<img src="https://i.imgur.com/sAPJ9eF.png">](https://i.imgur.com/sAPJ9eF.png)
[<img src="https://i.imgur.com/5Ch24nV.png">](https://i.imgur.com/5Ch24nV.png)
