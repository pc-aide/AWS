# Encryption Patterns & Envelope Encryption

## Doc

## Acronym
* KMS - Key Management Service
* IAM - Identity & Access Management
* CMK - Custom Master Key
* DEK - Data Encryption Key

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
[<img src="https://i.imgur.com/9wFus4b.png">](https://i.imgur.com/9wFus4b.png)

---

## Decrypt envelope data
[<img src="https://i.imgur.com/238Veqm.png">](https://i.imgur.com/238Veqm.png)

---

## Encryption SDK
* The AWS Encryption SDK implemented Envelope Encryption for us
* The Encryption SDK also exists as a CLI tool we can install
* Implementations for Java, Python, C, JavaScript
* **Feature - Data Key Caching**:
    * re-use data instead of creating new ones for each encryption
    * Helps with reducing the number of calls to KMS with a security trade-off
    * Use LocalCryptoMaterialsCache (max age, max bytes, max number of messages)
    
---

## KMS Symmetric - API Summary
* **Encrypt**: encrypt up to 4 KB of data through KMS
* **GenerateDataKey**: geneates a unique symmetric data key (DEK)
    * returns a plaintext copy of the data key
    * AND a copy that is encrypted under the CMK that you specify
* **GeneateDataKeyWithutPlaintext**:
    * Generate a DEK to use at some point (not immediately)
    * DEK that is encrypted under the CMK that you specify (must use Decrypt later)
* **Decrypt**: decrypt up to 4 KB of data (including Data Encryption Keys)
* **GenerateRandom**: Returns a random byte string
