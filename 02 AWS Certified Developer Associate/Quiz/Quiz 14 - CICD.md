# Quiz 14 - CI/CD

## Questions
1) CICD stands for...
    * Continuous Intervention & Continuous Delievery
    * Continuous Integration & Continuous Delievery
    * Continuus Inegration & Continuous Development
* [Answer](https://i.imgur.com/7uWXMpx.png)
2) Which AWS Service helps you run automated test in your CICD?
    * CodeCommit
    * CodeBuild
    * CodePipeline
    * CodeDeploy
* [Answer](https://i.imgur.com/H0eb8No.png)
3) You are looking to automatically trigger a code analysis at each commit in CodeCommit to ensure your developers
   haven't committed secret credentials. How can you achieve this?
    * Setup AWS CloudWatch Events in CodeCommit
    * Setup AWS SNS/ Lambda integration in CodeCommit
    * Setup SES in CodeCommit
* [Answer](https://i.imgur.com/BqbToFb.png)
4) You want to send email alerts anytime pull requests are open or comments are added to commits in CodeCommit. You should use
    * AWS SES
    * AWS SNS
    * AWS CloudWatch Events
* [Answer](https://i.imgur.com/mzNI9vK.png)
5) CodeCommit doesn't support the following authentication
    * IAM credentials helper with AWS CLI & git
    * SSH Keys in user profiles
    * HTTPS credentials in user profiles
    * HTTP public access
* [Answer](https://i.imgur.com/ycf83z2.png)
6) You want to give a colleague that has an IAM User in another AWS Account access to your CodeCommit repository. How should you achieve that?
    * Share your SSH key with them
    * Generate HTTPS credentials & share that
    * Setup an IAM Role in your account & teell him to use STS cross-account to assure that role
* [Answer](https://i.imgur.com/j8HRTiN.png)
7) Your CodePipeline hasn't deployed code to Elastic Beanstalk even though you've pushed code to your CodeCommit
   repository. It used to work 10 minutes ago. What reason is the most likely to explain that situation?
    * IAM permissions are wrong
    * CodePipeline is waiting for manual approval
    * You codeBuild stage probably failed some tests
    * Someone has deleted the EB environment
* [Answer](https://i.imgur.com/d0grSq2.png)
8) Your manager wants to receive emails when your CodePipeline fails in order to take action. How do you do it?
    * Setup an AWS CloudWatch Event Rule
    * Setup an SNS notification
    * Setup a SES email
* [Answer](https://i.imgur.com/2NhkeJu.png)
9) Which AWS Services allow you to track and audit API calls made to and from CodePipeline?
    * AWS CodeBuild
    * AWS CloudTrail
    * AWS IAM
    * AWS EB
* [Answer](https://i.imgur.com/AOOOpAA.png)
10) Where should the buildspec.yml file be placed in your code for CodeBuild to work properly?
    * in the CodeBuild/ directory
    * in the CodeCommit/ directory
    * at the root of your code
* [Answer](https://i.imgur.com/lldGHNd.png)
11) Your CodeBuild has failed. What isn't a solution to troubleshoot what happened?
    * Look through logs in AWS CloudWatch logs
    * Look through logs in AWS S3
    * SSH into the CodeBuild container to debug from there
    * Run CodeBuild locally to reproduce the build
* [Answer](https://i.imgur.com/jYqKgBb.png)
12) You would like to improve the performance of your CodeBuild build. You realize that 15 minutes at each build
    is spent on pulling dependencies from remote repositories and that takes a while. What should you do to drastically speed up the build time?
    * commit dependencies in the code
    * Change buildspec.yml to enable dependencies caching in Amazon S3
    * Remove all the dependencies
* [Answer](https://i.imgur.com/97Po0i0.png)
13) You would like to deploy static web files to Amazon S3 automatically, after generating the static websites from markdown files.
    Which services should you use for this?
    * CodeCommit + CodePipeline
    * CodePipeline + CodeBuild
    * CodePipeline + CodeDeploy
    * CodeDeploy
* [Answer](https://i.imgur.com/lEvEatH.png)
14) What's the proper order of events in CodeDeploy?
    * Install, Stop Application, Start Application, AfterInstall
    * Install, Stop Application, AfterInstall, Start Application
    * Stop Application, Before Install, Start Application, After Install
    * Stop Application, Bore Install, After Install, Start Application
* [Answer](https://i.imgur.com/kP0qpIt.png)
15) Which hook step should be used in appspec.yml file to ensure the application is properly running after being deployed?
    * AfterInstall
    * ValidateService
    * ApplicationStart
    * AllowTraffic
* [Answer](https://i.imgur.com/ZQBviIc.png)
16) You've created a fleet of EC2 & on-premise instances and you're trying to run your first CodeDeploy. It doesn't work, why? 
    * You've probably forgotten to install & start the CodeDeploy agent
    * CodeDeploy doesn't work On Premise instances
    * You've forgottent to open ports on th CodeDeploy service security group
* [Answer](https://i.imgur.com/WQRQBFk.png)
17) You would like to have a one-stop dashboard for all the CICD needs of one of your projects. You don't need
    heavy control of the individual configuration of each components in your CICD, but need to be able to get
    a holistic view of your projects. Which service do you recommend?
    * CodeBuild
    * CodePipeline
    * CodeStar
    * CodeDeploy
* [Answer](https://i.imgur.com/41fCJZU.png)
