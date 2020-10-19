# Encryption Patterns & Envelope Encryption

## Doc

## Acronym
* KMS - Key Management Service

## API - Encrypt & Decrypt
* limit file < 4 KB:

[<img src="https://i.imgur.com/qHjeJM5.png">](https://i.imgur.com/qHjeJM5.png)

---

## Envelope Encryption
* KMS Encrypt API call has a limit of 4 KB
* If you want to encrypt > 4 KB, we need to use **Envelope Encryption**
* The main API that will hep us is the **GenerateDataKey** API
* <ins>For the exam</ins>: anything over 4 KB of data that needs to be encrypted must use
  the **Envelope Encryption == GenerateDataKey API**
  
---

## GenerateDataKey API
