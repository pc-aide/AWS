# Limits

## Acronym
* KMS - Key Management Service
* SSE-KMS - Server-Side-Encryption-KMS
* DEK - Data Encryption Key

## Doc

## KMS Request Quotas
* When you exceed a request quota, you get a **ThrottlingException**
    * Ex.:
````txt
You have exceed the rate at which you may call KMS. Reduce the frequency of your calls.
(Service: AWSKMS; status Code: 400; Error Code: ThrottlingException; Request ID: <ID>
````
* To respond, use **exponential backoff** (backoff & retry)
* For cryptographic operations, they share a quota
* This includes requests made by AWS on your behalf (ex: SSE-KMS)
* For GenerateDataKey, condider using DEK caching from the Encryption SDK
* You can **request Request Quotas increase through API or AWS support (open a ticket)**

---

## KMS Request Quotas
| API Operation                                                                                                                                                               | Request quotas (per second)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Decrypt<br>Encrypt<br>GenerateDataKey (symmetric)<br>GenerateDataKeyWithoutPlainText (symmetric)<br>GenerateRandom<br>ReEncrypt<br>Sign (asymmetric)<br>Verify (asymmetric) | These shared quotas vary with the Region &<br>the type of CMK used in the request. Each quotas is<br>calculated separately.<br><br>**Symettric CMK quota**:<br>\* 5 500 (shared)<br>\* 10k (shared in the following Regions:<br>\* us-east-2, ap-southeast-1, ap-southeast-2,<br>ap-northeast-1, eu-central-1, eu-west-2<br>\* 30k (shared) in the following Regions:<br>\* us-east-1, us-west-2, eu-west-1<br><br>**Asymmetric CMK quota**:<br>\* 500 (shared) for RSA CMKs<br>\* 300 (shared) for Elliptic curve (ECC) CMKs |

