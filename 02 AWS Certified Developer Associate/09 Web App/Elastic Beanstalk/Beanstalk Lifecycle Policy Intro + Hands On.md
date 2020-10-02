# Beanstalk Lifecycle Policy Intro + Hands On

## Doc
* [Configuring application version lifecycle settings](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/applications-lifecycle.html?icmpid=docs_elasticbeanstalk_console)

## Acronym
* Prd - Production

## Beanstalk Lifecycle Policy
* Beanstalk can store at most 1k apps versions
* If you don't remove old versions, you won't be able to deploy anymore
* To phase out old application versions, use a **lifecle policy**
    * Based on time (old versins are removed)
    * Based on space (when you have too many versions)
* Versions that are currently used won't be delete
* Option not delete the source bundle in S3 to prevent data loss

---

## Demo
* Beanstalk\app-prd\applications versions:

[<img src="https://i.imgur.com/sLclDDr.png">](https://i.imgur.com/sLclDDr.png)

* Settings
    * Lifecycle policy: Enable
    * RadioButton: set the application versions limit by age
    * Retention: Retain source bundle in S3
    
[<img src="https://i.imgur.com/Pk37BGj.png">](https://i.imgur.com/Pk37BGj.png)

* S3:

[<img src="https://i.imgur.com/SRFjuvg.png">](https://i.imgur.com/SRFjuvg.png)
