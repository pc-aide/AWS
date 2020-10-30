# §08 - IaC

## Questions
1. Which of the AWS CloudFormation template sections is/are required?
    * A. AWSTemplateFormatVersion
    * B. Parameters
    * C. Metadata
    * D. Resources
    * E. All of the above
2. You are writing an AWS CloudFormation template and would like to create an output
value corresponding to your application’s website URL. The application is composed of
two application servers in a private subnet behind an Elastic Load Balancing load balancer.
The application servers read from the Amazon RDS
database instance. The logical IDs of the instances are AppServerA and AppServerB. The
logical IDs of the load balancer and database are AppLB and AppDB, respectively
````json
"Outputs": {
  "AppEndpoint" : {
    "Description" : "URL to access the application",
    "Value" : "Value to return"
  }
}
````
* Which code correctly completes the previous output declaration?
   * A. `{ "Fn::Join": [ "", [ https://, { "Ref": "AppLB" }, "/login.php" ] ] }`
   * B.
````json
{ "Fn::Join": [ "", [ https://, { "Fn::GetAtt": [ "AppServerA",
"PublicDNSName" ] }, "/login.php" ] ] }
````
   * C.
````json
{ "Fn::Join": [ "", [ https://, { "Ref": [ "AppLB", "DNSName" ] },
"/login.php" ] ] }
````
   * D. 
````json
{ "Fn::Join": [ "", [ https://, { "Fn::GetAtt": [ "AppDB", "Endpoint 
.Address" ] }, "/login.php" ] ] }
````
   * E. 
````json
{ "Fn::Join": [ "", [ https://, { "Fn::GetAtt": [ "AppLB", "DNSName" ] },
"/login.php" ] ] }
````
3. An AWS CloudFormation template you have written uses a CreationPolicy to ensure
that video transcoding instances launch and configure before the application server
instances so that they are available before users are able to access the website. However,
you are finding that the stack always reaches the creation policy’s timeout value before the
transcoding instances complete setup.<br/>Why could this be? (**Select THREE**.)
      * A. The user data script does not include a call to cfn-signal
      * B. The instance could not be launched because of account limits.
      * C. The user data script fails before reaching the cfn-signal step
      * D. The instance cannot connect to the AWS CloudFormation endpoint when calling cfn-signal.
4. When you attempt to update an Amazon RDS instance in your AWS CloudFormation stack, you experience a Resource failed to
stabilize error, which causes the stack to roll back any changes you attempted.</br>What might be the cause of this error, and how could it be resolved?
      * A. The database is corrupted and cannot be updated. Take a snapshot of the database,
and use it to create a replacement.
      * B. The database took too long to update. Remove the database from the AWS
CloudFormation stack by applying a DeletionPolicy of Retain, and manage the
stack using the Amazon RDS console or AWS CLI.
      * C. The database took too long to update, and the session credentials used by AWS
CloudFormation timed out. Use a service role to perform the update.
      * D. You have attempted to perform an update that is not supported by Amazon RDS.
Review the specification documentation and attempt a valid update.
      * E. I/O has not been halted on the database before performing the update, and AWS
CloudFormation timed out waiting for database transactions to halt. Temporarily
block I/O and attempt the update again.
5. A custom resource associated with AWS Lambda in your stack creates successfully;
however, it attempts to update the resource result in the failure message Custom Resource
failed to stabilize in the expected time. After you add a service role to extend the
timeout duration, the issue still persists.<br/>What may also be the cause of this error?
      * A. The custom resource defined a function for handling the CREATE action but did not do
the same for the UPDATE action; thus, a success or failure signal was not sent to AWS
CloudFormation.
      * B. The service role does not have appropriate permissions to invoke the custom resource
function
      * C. The custom resource function no longer exists
      * D. All of the above
6. After you deploy an AWS SAM template to AWS
CloudFormation, can you view the original template? Why or why not?
      * A. No, after the template is submitted and the AWS::Serverless transform is executed,
an AWS CloudFormation-supported template is generated.
      * B. Yes, the original template is saved and accessible using the get-stack-template AWS
CLI command.
      * C. Yes, it is saved in the Amazon S3 bucket created by
AWS CloudFormation for AWS SAM templates.
      * D. No, AWS CloudFormation does not retain processed templates
7. When defining an AWS SAM template, how can you create an Amazon API Gateway as part of the stack?
      * A. By defining an AWS::ApiGateway::RestApi resource and any associated
AWS::ApiGateway::Method resources
      * B. One will be created automatically for you whenever AWS::Serverless::Function
resources are declared with one or more Events.
      * C. By defining an AWS::Serverless::Api and providing an inline or external Swagger
definition
      * D. AWS::ApiGateway::RestApi resources are not supported in AWS SAM templates
      * E. A,B, & C
8. Which of these helper scripts performs updates to OS configuration when an AWS
CloudFormation stack updates?
      * A. cfn-hup
      * B. cfn-init
      * C. cfn-signal
      * D. cfn-update
9. Which of these options allows you to specify a required number of signals to mark the
resource as CREATE_COMPLETE?
      * A. Wait Condition
      * B. Wait Condition Handler
      * C. CreationPolicy
      * D. WaitCount
10. How would you preview the changes a stack update will make without affecting any
resources in your account?
      * A. Create a change set.
      * B. Perform the stack update, and then manually roll back
      * C. Perform the stack update on a test stack
      * D. Do a manual diff of both templates
11. How would you access a property of a resource created in a nested stack?
      * A. This cannot be done.
      * B. In the child stack, declare the resource property as a stack output. In the parent
stack, use Fn::GetAtt and pass in two parameters, the child stack logical ID and
Outputs.NestedStackOutputName
      * C. In the child stack, export the resource property. In the parent stack, import the
exported value.
      * D. Use the cross-stack references
12. By default, with what permissions will AWS CloudFormation stack operations perform?
      * A. Full administrator
      * B. The permissions of the user performing the operation
      * C. The AWS CloudFormation service role
      * D. The AWS CloudFormation does not use permissions
13. An AWS CloudFormation template declares two resources: an AWS Lambda function and
an Amazon DynamoDB table. The function code is declared inline as part of the template
and references the table. In what order will AWS CloudFormation provision the two
resources?
      * A. Amazon DynamoDB table, AWS Lambda function
      * B. AWS Lambda function, Amazon DynamoDB table
      * C. This cannot be determined ahead of time
      * D. This depends on the template
14. Which occurs during a replacing update?
      * A. The resource becomes unavailable
      * B. The resource physical ID changes.
      * C. A new resource is created
      * D. The original resource is deleted during the cleanup phase.
      * E. All of the above
15. Which of the update types results in resource downtime? (**Select TWO**.)
      * A. Update with No Interruption
      * B. Update with Some Interruption
      * C. Replacing Update
      * D. Update with No Data
      * E. Static Update
16. What must occur before a stack that exports an output can be deleted?
      * A. Any stacks importing the exported value must remove the import.
      * B. The export must be removed from the stack.
      * C. Nothing is required.
      * D. The stack must be deleted.
17. If an AWS CloudFormation stack is in UPDATE_IN_PROGRESS state, which of the states are
possible transitions? (**Select THREE**.)
      * A. UPDATE_ROLLBACK_COMPLETE
      * B. UPDATE_FAILED
      * C. UPDATE_ROLLBACK_FAILED
      * D. UPDATE_COMPLETE
      * E. UPDATE_COMPLETE_CLEANUP_IN_PROGRESS
18. What does it mean when an AWS CloudFormation stack is in
UPDATE_COMPLETE_CLEANUP_IN_PROGRESS state?
      * A. The stack has failed to update, and it is removing newly created resources
      * B. The stack has successfully updated, and it is removing old resources
      * C. The stack has successfully updated, and it is removing new resources
      * D. The stack has failed to update, and it is removing old resources.
19. Which of the formats are valid for an AWS CloudFormation template? (**Select TWO**.)
      * A. YAML
      * B. XML
      * C. JSON
      * D. Markdown
      * E. LaTeX
20. What are some challenges to consider when using the AWS CLI or AWS SDKs to provision and manage
infrastructure compared to AWS CloudFormation?
      * A. Reduction of human error
      * B. Repeatable infrastructure
      * C. Reduced IAM permissions requirements
      * D. Versionable infrastructure
      * E. All of the above
21. What does a service token represent in a custom resource declaration?
      * A. The AWS service that receives the request
      * B. The Amazon SNS or AWS Lambda resource ARN that receives the request
      * C. The on-premises server IP address that receives the request
      * D. The type of action to take
      * E. The commands to execute for the custom resource
22. You are creating a custom resource associated with AWS Lambda that will execute several
database functions in an Amazon RDS database instance. As part of this, the functions will return data you would like to use in other
resources declared in your AWS CloudFormation template<br/>How would you best pass this data to the other resources declared in the template?
      * A. Store the data in a JSON file in an Amazon S3 bucket, and use the AWS CLI to download the object
      * B. Store the output data in AWS Systems Manager Parameter Store, and query the parameter store using the AWS CLI.
      * C. Use custom resource outputs to declare the returned data as resource properties. Then, query the properties using the Fn::GetAtt intrinsic function.
      * D. This cannot be accomplished.
* [Answers]()
    * [Explications]()
* Score:
    * [28-10-2020 AM] 9/22 ≈ 41%
