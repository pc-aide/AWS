# private-key
* private-key = RSA Private key

## permissions

* if we have this problem:
````text
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for 'private-key.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
Load key "private-key.pem": bad permissions
ec2-user@35.182.252.72: Permission denied (publickey,gssapi-keyex,gssapi-with-mic).
````

* check out permission on this...
````bash
ls -l private-key
````
[<img src="https://i.imgur.com/Qj45ivo.png">](https://i.imgur.com/Qj45ivo.png)

* we need chmod 400 private-key
````bash
chmod 400 private-key
````
[<img src="https://i.imgur.com/AWzZUYv.png">](https://i.imgur.com/AWzZUYv.png)
