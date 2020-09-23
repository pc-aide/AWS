# S3 Versioning

## Doc

## Acronym

## Introduction
* You can vesion your files in Amazon S3
* It's enabled at the **bucket level**
* Same key overwrite will increment the ""version"": 1,2,3,...
* It's best practice to version your buckets
    * Protect against unintended deletes (ability to restore a version)
    * Easy roll back to previous version
* Notes:
    * Any file that is not versioned prior to enabling versioning will have sersion "null"
    * Suspending versioning does nt delete the previous versions
    
---

## Demo
* Enabled Versioning

[<img src="https://i.imgur.com/DM7ipkc.png">](https://i.imgur.com/DM7ipkc.png)
[<img src="https://i.imgur.com/USWc2wC.png">](https://i.imgur.com/USWc2wC.png)
[<img src="https://i.imgur.com/UuRyHWk.png">](https://i.imgur.com/UuRyHWk.png)
[<img src="https://i.imgur.com/gpPOASG.png">](https://i.imgur.com/gpPOASG.png)
[<img src="https://i.imgur.com/A9vwN7Q.png">](https://i.imgur.com/A9vwN7Q.png)
[<img src="https://i.imgur.com/Qa4Flf0.png">](https://i.imgur.com/Qa4Flf0.png)
[<img src="https://i.imgur.com/4Xoo7CJ.png">](https://i.imgur.com/4Xoo7CJ.png)
[<img src="https://i.imgur.com/8NXXJSQ.png">](https://i.imgur.com/8NXXJSQ.png)
