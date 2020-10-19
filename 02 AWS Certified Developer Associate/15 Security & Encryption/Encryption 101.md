# Encryption 101

## Doc

## Acronym
* SSL - Secure Socket Layers
* MITM - Man In The Middle attack
* EBS - Elastic Block Store

## Encryption in flight (SSL)
* Data is encrypted before sending & decrypted after receiving
* SSL certificates help with encryption (HTTPS)
* Encryption in flight ensures no MITM can happen

## Diagram
[<img src="https://i.imgur.com/2Z150aP.png">](https://i.imgur.com/2Z150aP.png)

---

## Server side encryption at rest
* Data is encrypted after being received by the server
* Data is decrypted before being sent
* It's stored in an encrypted form thansk to a key (usually a data key)
* The encryption/decryption keys must be managed somehwere & the server must have access to it

### Diagram
[<img src="https://i.imgur.com/Q0qmcv9.png">](https://i.imgur.com/Q0qmcv9.png)

---

## Client side encryption
* Data is encrypted by the client & never decrypted by the server
* Data will be decrypted by a receiving client
* The server should not be able to decrypted the data
* Could leverage Envelope Encryption

### Diagram
[<img src="https://i.imgur.com/xfl9ut3.png">](https://i.imgur.com/xfl9ut3.png)
