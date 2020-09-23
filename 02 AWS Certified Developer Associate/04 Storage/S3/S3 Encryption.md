# S3 Encryption

## Acronym
* S3 - Simple Storage Service
* KMS - Key Management Service
* SSE - Server Side Encryption
* SSL - Secure Sockets Layers
* TLS - Transport Layer Security

## Doc

## Introduction
* There are 4 mehtods of encrypting objects in S3
    * SSE-S3: encrypts S3 objects using keys handled & managed by AWS
    * SSE-KMS: leverage AWS KMS to manage encryption keys
    * SSE-C: when you want ot manage your own encryption keys
    * Client Side Encryption

---

## SSE-S3
* SSE-S3: encryption using keys handled & managed by Amazon S3
* Object is encrypted **server side**
* AES-256 encryption type
* Must set header: **"x-amz-server-side-encryption":"AES256"**

### Diagram
[<img src="https://i.imgur.com/1jF9UIJ.png">](https://i.imgur.com/1jF9UIJ.png)

---

## SSE-KMS
* SSE-KMS: encryption using keys handled & managed by KMS
* KMS Advantages: user control + audit trail
* Object is encrypted server side
* Must set header: **"x-amz-server-side-encryption":"aws:kms"**

### Diagram
[<img src="https://i.imgur.com/InDlrVs.png">](https://i.imgur.com/InDlrVs.png)

---

## SSE-C
* SSE-C: server-side encryption using data keys fully managed by the customer outside of AWS
* Amazon S3 does not store the encryption key you provide
* **HTTPS must be used**
* Encryption key must provided in HTTP headers, for every HTTP headers, for every HTTP request made

### Diagram
[<img src="https://i.imgur.com/sK8CbHK.png">](https://i.imgur.com/sK8CbHK.png)

---

## Client Side Encryption
* Client library such as the Amazon S3 Encryption client
* Clients must encrypt data themselves before sending to S3
* Clients must decrypt data themselves when retrieving from S3
* Customer fully manages the keys & encryption cycle

### Diagram
[<img src="https://i.imgur.com/tSJjUdn.png">](https://i.imgur.com/tSJjUdn.png) 

---

## Encryption in transit (SSL/TLS)
* Amazon S3 exposes:
    * HTTP endpoint: non encrypted
    * HTTPS endpoint: encryption in flight
* Most clients would use the HTTPS endpoint by default
* HTTPS is mandatory for SSE-C
* Encryption in flight is also called SSL/TLS

---

## Demo
* Your file.png no encrypted

[<img src="https://i.imgur.com/ySxxeKX.png">](https://i.imgur.com/ySxxeKX.png)

* Upload another file + Encryption.S3_Master-key:

[<img src="https://i.imgur.com/iV7KT8u.png">](https://i.imgur.com/iV7KT8u.png)
[<img src="https://i.imgur.com/2sV4R0Y.png">](https://i.imgur.com/2sV4R0Y.png)

* Idem with KMS:

[<img src="https://i.imgur.com/J0Qfecc.png">](https://i.imgur.com/J0Qfecc.png)
[<img src="https://i.imgur.com/wBqhzPr.png">](https://i.imgur.com/wBqhzPr.png)
[<img src="https://i.imgur.com/fXT09b5.png">](https://i.imgur.com/fXT09b5.png)
[<img src="https://i.imgur.com/hqdDTpM.png">](https://i.imgur.com/hqdDTpM.png)

### Default encryption
* Properties\Default encryption:

[<img src="https://i.imgur.com/t0LglYx.png">](https://i.imgur.com/t0LglYx.png)
[<img src="https://i.imgur.com/6A2ro2G.png">](https://i.imgur.com/6A2ro2G.png)
[<img src="https://i.imgur.com/TAelpMM.png">](https://i.imgur.com/TAelpMM.png)

* Upload a new file.png

[<img src="https://i.imgur.com/JrcC71q.png">](https://i.imgur.com/JrcC71q.png)
