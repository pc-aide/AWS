# CodeCommit Hands On Part 1

## Acronym
* SNS - Simple Notification Service

## Doc

## Intro
* CodeCommit:

[<img src="https://i.imgur.com/7Jnvfpe.png">](https://i.imgur.com/7Jnvfpe.png)

* Create repository:
    * Repository name: nodejs-app
    * Create
    
[<img src="https://i.imgur.com/BupOx1a.png">](https://i.imgur.com/BupOx1a.png)

* Code:

[<img src="https://i.imgur.com/fges2lU.png">](https://i.imgur.com/fges2lU.png)

* upload a file
* code_index.html:
````html
<!DOCTYPE html>
<html>
  <head>
    <title>Elastic Beanstalk</title>
    <style>
      body {
        color: #ffffff;
        font-family: Arial, sans-serif;
        font-size:14px;
        -moz-transition-property: text-shadow;
        -moz-transition-duration: 4s;
        -webkit-transition-property: text-shadow;
        -webkit-transition-duration: 4s;
        text-shadow: none;
      }
      body.blurry {
        -moz-transition-property: text-shadow;
        -moz-transition-duration: 4s;
        -webkit-transition-property: text-shadow;
        -webkit-transition-duration: 4s;
        text-shadow: #fff 0px 0px 25px;
      }
      a {
        color: #55aaff;
      }
      .textColumn, .linksColumn {
        padding: 2em;
      }
      .textColumn {
        position: absolute;
        top: 0px;
        right: 50%;
        bottom: 0px;
        left: 0px;

        text-align: right;
        padding-top: 11em;
        background-color: blue;

      }
      .textColumn p {
        width: 75%;
        float:right;
      }
      .linksColumn {
        position: absolute;
        top:0px;
        right: 0px;
        bottom: 0px;
        left: 50%;

        background-color: #33342D;
      }

      h1 {
        color: #33342D;
        font-size: 500%;
        font-weight: normal;
        margin-bottom: 0em;
      }
      h2 {
        font-size: 200%;
        font-weight: normal;
        margin-bottom: 0em;
      }
      ul {
        padding-left: 1em;
        margin: 0px;
      }
      li {
        margin: 1em 0em;
      }
    </style>
  </head>
  <body>
    <div class="textColumn">
      <h1>Congratulations</h1>
      <p>Your first AWS Elastic Beanstalk Node.js application is now running on your own dedicated environment in the AWS Cloud</p>
    </div>
    <div class="linksColumn">
      <h2>What's Next?</h2>
      <ul>
        <li><a href="http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html">AWS Elastic Beanstalk overview</a></li>
        <li><a href="http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/concepts.html">AWS Elastic Beanstalk concepts</a></li>
        <li><a href="http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_nodejs_express.html">Deploy an Express Application to AWS Elastic Beanstalk</a></li>
        <li><a href="http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_nodejs_express_elasticache.html">Deploy an Express Application with Amazon ElastiCache to AWS Elastic Beanstalk</a></li>
        <li><a href="http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_nodejs_geddy_elasticache.html">Deploy a Geddy Application with Amazon ElastiCache to AWS Elastic Beanstalk </a></li>
        <li><a href="http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/create_deploy_nodejs_custom_container.html">Customizing and Configuring a Node.js Container </a></li>
        <li><a href="http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.loggingS3.title.html">Working with Logs</a></li>
      </ul>
    </div>
  </body>
</html>
````

* Commit changes

[<img src="https://i.imgur.com/jsOUPxd.png">](https://i.imgur.com/jsOUPxd.png)
[<img src="https://i.imgur.com/yuTWVxv.png">](https://i.imgur.com/yuTWVxv.png)

* Our repositories:

[<img src="https://i.imgur.com/ClguD1Z.png">](https://i.imgur.com/ClguD1Z.png)

* Pull requests:

[<img src="https://i.imgur.com/5Cy53Fk.png">](https://i.imgur.com/5Cy53Fk.png)

* Commits:

[<img src="https://i.imgur.com/NdUE5lx.png">](https://i.imgur.com/NdUE5lx.png)
[<img src="https://i.imgur.com/9EsBTmE.png">](https://i.imgur.com/9EsBTmE.png)
[<img src="https://i.imgur.com/LTja4t0.png">](https://i.imgur.com/LTja4t0.png)

* Branches:

[<img src="https://i.imgur.com/qFNWH7G.png">](https://i.imgur.com/qFNWH7G.png)

* Settings:

[<img src="https://i.imgur.com/UgqqW4K.png">](https://i.imgur.com/UgqqW4K.png)

* Notification ruls:

[<img src="https://i.imgur.com/cgkeQcK.png">](https://i.imgur.com/cgkeQcK.png)

* Create notification rule:
      * Notifacation name: Demo-Notification-Rule
      * Events Trigger: Select all
      * Create target:
         * Target type: SNS topic
         * Topic name: CodeCommit-Lab
* Summit

[<img src="https://i.imgur.com/NvdtApm.png">](https://i.imgur.com/NvdtApm.png)
[<img src="https://i.imgur.com/C3sb0Qo.png">](https://i.imgur.com/C3sb0Qo.png)
[<img src="https://i.imgur.com/OrDMVRN.png">](https://i.imgur.com/OrDMVRN.png)

* Create trigger (Source\Settings\Trigger):
   * Trigger name: Demo-trigger
   * Events: Push to existing branch
   * Branch names: master
   * Service details\Amazon SNS
   * SNS topic: CodeCommit-Lab
   
[<img src="https://i.imgur.com/pXlXEnR.png">](https://i.imgur.com/pXlXEnR.png)
[<img src="https://i.imgur.com/M8oiIZd.png">](https://i.imgur.com/M8oiIZd.png)
