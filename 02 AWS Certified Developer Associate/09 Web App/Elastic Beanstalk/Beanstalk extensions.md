# Beanstalk extensions

## Acronym
* RDS - Relational Database Service

## Doc
* [Environment properties and other software settings](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/environments-cfg-softwaresettings.html?icmpid=docs_elasticbeanstalk_console)

## Intro
* A zip file containing our code must be deployed to Elastic Beanstalk
* All the parameters set in the UI can be configured with code using files
* Requirements:
    * in the .ebExtensions/ directory in the root of source code
    * YAML/JSON format
    * **.config** extensions (example: loggin.config)
    * Able to modify some default settings using: option_settings
    * Ability to add resources such as RDS, ElastiCache, DynamoDB, etc
* Resources managed by **.ebExtensions** get deleted if the environment goes away 

---

## Demo
* this architecture files
    * nodejs-v3-ebextensions/
      * app.js
      * cron.yaml
      * Icon
      * index.html
      * package.json
      * .ebextensions/
        * environment-variables.config
        * Icon
        
* environment-variables.config:
````yaml
# You must place this file in .ebextensions
# And must have a .config file name
# So the file is at  .ebextensions/environment-variables.config
# Note: Even though the markup language is YAML, you must use use .config extension

option_settings:
  # See: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/command-options-general.html#command-options-general-elasticbeanstalkapplicationenvironment
  aws:elasticbeanstalk:application:environment:
    DB_URL: "jdbc:postgresql://rds-url-here.com/db"
    DB_USER: username
    
# This format works too:
# option_settings:
#   _ namespace: namespace
#     option_name: option name
#     value: option value

# See: https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/ebextensions-optionsettings.html
````

[<img src="https://i.imgur.com/JosfLpw.png">](https://i.imgur.com/JosfLpw.png)
[<img src="https://i.imgur.com/6Ne9Yqb.png">](https://i.imgur.com/6Ne9Yqb.png)
[<img src="https://i.imgur.com/goRYsHD.png">](https://i.imgur.com/goRYsHD.png)

* upload your code in dev-env:

[<img src="https://i.imgur.com/o3I3VLs.png">](https://i.imgur.com/o3I3VLs.png)
[<img src="https://i.imgur.com/cKwwd8F.png">](https://i.imgur.com/cKwwd8F.png)

* Browswer with downtime (503 gateway):

[<img src="https://i.imgur.com/IdnEeBy.png">](https://i.imgur.com/IdnEeBy.png)
[<img src="https://i.imgur.com/G4Vuj0t.png">](https://i.imgur.com/G4Vuj0t.png)

* Dashboard dev-env:

[<img src="https://i.imgur.com/pl65IPO.png">](https://i.imgur.com/pl65IPO.png)

* Configuration\software\Edit

[<img src="https://i.imgur.com/AnyNnVP.png">](https://i.imgur.com/AnyNnVP.png)

* Environment properties
    * DB_URL
    * DB_user
