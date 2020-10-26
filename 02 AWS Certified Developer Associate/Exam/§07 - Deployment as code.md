# §07 - Deployment as code

## Questions
1. You have two AWS CodeDeploy applications that deploy to the same Amazon EC2 Auto
Scaling group. The first deploys an e-commerce app, while the second deploys custom
administration software. You are attempting to deploy an update to one application but
cannot do so because another deployment is already in progress. You do not see any
instances undergoing deployment at this time. What could be the cause of this?
      * A. If both deployment groups reference the same Auto Scaling group, a failure of the
first group’s deployment can block the second until the deployment times out. Since the
instance that failed deployment has been terminated from the Auto Scaling group, the AWS
CodeDeploy agent is unable to provide results to the service.
      * B. The AWS CodeDeploy agent is not installed on the instances as part of the launch
configuration user data script.
      * C. If both deployment groups reference the same Auto Scaling group, a failure of the first
group’s deployment can block the second until the deployment times out. Since the instance
that failed deployment has been terminated from the Auto Scaling group, the AWS
CodeDeploy service is unable to request status updates from the Amazon EC2 API.
      * D. The AWS CodeDeploy agent is not installed in the AMI
being used.
2. If you specify a hook script in the ApplicationStop lifecycle event of an AWS CodeDeploy
appspec.yml, will it run on the first deployment to your instance(s)?
      * A. Yes
      * B. No
      * C. The ApplicationStop lifecycle event does not exist.
      * D.  It will run only if your application is running.
3. If a single pipeline contains multiple sources, such as an AWS CodeCommit repository and
an Amazon S3 archive, under what circumstances will the pipeline be triggered?
      * A. When either a commit is pushed to the repository or the archive is updated, regardless
of timing.
      * B. When a commit is pushed to the repository and the archive is updated at the same time.
      * C. When either a commit is pushed to the repository or the archive is updated, but not
when both are updated at the same time.
      * D. AWS CodePipeline does not support multiple sources in the same pipeline.
4. If you want to implement a deployment pipeline that deploys both source files and large binary
objects to instance(s), how would you best achieve this while taking cost into consideration?
      * A. Store both the source files and binary objects in AWS CodeCommit.
      * B. Build the binary objects into the AMI of the instance(s) being deployed. Store the
source files in AWS CodeCommit.
      * C. Store the source files in AWS CodeCommit. Store the binary objects in an Amazon S3
archive.
      * D. Store the source files in AWS CodeCommit. Store the binary objects on an Amazon EBS volume, taking snapshots of the volume whenever a
new one needs to be created.
      * E. Store the source files in AWS CodeCommit. Store the binary objects in Amazon S3 and
access them from an Amazon CloudFront distribution.
5. Your team is building a deployment pipeline to a sensitive application in your environment
using AWS CodeDeploy. The application consists of an Amazon EC2 Auto Scaling group
of instances behind an Elastic Load Balancing load balancer. The nature of the application
requires 100 percent availability for both successful and failed deployments. The development
team want to deploy changes multiple times per day.<br/>
How would this be achieved at the lowest cost and with the fastest deployments?
      * A. Rolling deployments with an additional batch
      * B. Rolling deployments without an additional batch
      * C. Blue/green deployments
      * D. Immutable updates
6. What would cause an access denied error when attempting to download an archive file
from Amazon S3 during a pipeline execution?
      * A. Insufficient user permissions for the user initiating the pipeline
      * B. Insufficient user permissions for the user uploading the Amazon S3 archive
      * C. Insufficient role permissions for the Amazon S3 service role
      * D. Insufficient role permissions for the AWS CodePipeline service role
7. How do you output build artifacts from AWS CodeBuild to AWS CodePipeline?
      * A. Write the outputs to STDOUT from the build container.
      * B. Specify artifact files in the buildspec.yml configuration file.
      * C. Upload the files to Amazon S3 from the build environment.
      * D. Output artifacts are not supported with AWS CodeBuild.
8. What would be the most secure means of providing secrets to an AWS CodeBuild
environment?
      * A. Create a custom build environment with the secrets included in configuration files.
      * B. Upload the secrets to Amazon S3 and download the object when the build job runs.
Protect the bucket and object with an appropriate bucket policy.
      * C. Save the secrets in AWS Systems Manager Parameter Store and query them as needed.
Encrypt the secrets with an AWS KMS key. Include
appropriate AWS KMS permissions to your build environment’s IAM role.
      * D. Include the secrets in the source repository or archive.
9. In which of the pipeline actions can you execute AWS Lambda functions?
      * A. Invoke
      * B. Deploy
      * C. Build
      * D. Approval
      * E. Test
10. In what ways can pipeline actions be ordered in a stage? (**Select TWO**.)
      * A. Series
      * B. Parallel
      * C. Stages support only one action each
      * D. FIFO
      * E. LIFO
11. If you would like to delete an AWS CloudFormation stack before you deploy a new one in
your pipeline, what would be the correct set of actions?
      * A. One action that specifies “Create or update a stack.”
      * B. Two actions: the first specifies “Create or update a stack,” and the second specifies
“Delete a stack.”
      * C. Three actions: the first specifies “Delete a stack,” the second specifies “Create or
update a stack,” and the third specifies “Replace a failed stack.”
      * D. Two actions: the first specifies “Delete a stack,” and the second specifies “Create or
update a stack.”
12. How can you connect to an AWS CodeCommit repository without Git credentials?
      * A. It is not possible
      * B. HTTPS
      * C. SSH
      * D AWS CodeCommit credential helper
13. Of the following, which event cannot be used to generate notifications to an Amazon
SNS topic from AWS CodeCommit without using a trigger?
      * A. Pull Request Creation
      * B. Commit Comments
      * C. Commit Creation
      * D. Pull Request Comments
14. Which pipeline actions support AWS CodeBuild projects? (**Select TWO**.)
      * A. Invoke
      * B. Deploy
      * C. Build
      * D. Approval
      * E. Test
15. Can data passed to build projects using environment variables be encrypted or protected?
      * A. Yes, this is supported natively by AWS CodeBuild.
      * B. No, it is not supported.
      * C. No, but this can be enabled in the console.
      * D. No, but this can be supported using other AWS products and services.
16. What is the only deployment type supported by on-premises instances?
      * A. In-place
      * B. Blue/green
      * C. Immutable
      * D. Progressive
17. If your AWS CodeDeploy configuration includes creation of a file, nginx.conf, but the
file already exists on the server (prior to the use of AWS CodeDeploy), what is the default
behavior that will occur during deployment?
      * A. The file will be replaced.
      * B. The file will be renamed nginx.conf.bak, and the new file will be created
      * C. The deployment will fail.
      * D. The deployment will continue, but the file will not be modified.
18. How does AWS Lambda support in-place deployments?
      * A. Function versions are overwritten during the deployment.
      * B. New function versions are created, and then version numbers are switched.
      * C. AWS Lambda does not support in-place deployments.
      * D. Function aliases are overwritten during the deployment.
19. What is the minimum number of stages required by a pipeline in AWS CodePipeline?
      * A. 0
      * B. 1
      * C. 2
      * D. 3
20. If an instance is running low on storage, and you find that there are a large number of
deployment revisions stored by AWS CodeDeploy, what can be done to free up this space
permanently?
      * A. Delete the old revisions.
      * B. Add an additional Amazon EBS volume.
      * C. Configure the AWS CodeDeploy agent to store fewer revisions.
      * D. Delete all of the revisions, and push all new code.
* [Answers](https://i.imgur.com/c7gfy0y.png)
    * [Explication](https://i.imgur.com/Q3oNAJl.png)
* Score: 13/20 = 65%
