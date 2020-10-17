# Policy Templates

## Doc
* [Policy template table](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-policy-templates.html#serverless-policy-template-table)

## Acronym
* SAM - Serverless Applicaion Model

## Intro
* list of templates to apply permissions to your Lambda Functions
* Full list available here
    * Policy template table:
    
| n  | Policy Template                                | Description                                                                                                                       |
|----|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| 1  | SQSPollerPolicy                                | Gives permission to poll an Amazon Simple Queue Service (Amazon SQS) queue.                                                       |
| 2  | LambdaInvokePolicy                             | Gives permission to invoke an AWS Lambda function, alias, or version.                                                             |
| 3  | CloudWatchDescribeAlarmHistoryPolicy           | Gives permission to describe CloudWatch alarm history.                                                                            |
| 4  | CloudWatchPutMetricPolicy                      | Gives permission to send metrics to CloudWatch.                                                                                   |
| 5  | EC2DescribePolicy                              | Gives permission to describe Amazon Elastic Compute Cloud (Amazon EC2) instances.                                                 |
| 6  | DynamoDBCrudPolicy                             | Gives create, read, update, and delete permissions to an Amazon DynamoDB table.                                                   |
| 7  | DynamoDBReadPolicy                             | Gives read-only permission to a DynamoDB table.                                                                                   |
| 8  | DynamoDBWritePolicy                            | Gives write-only permission to a DynamoDB table.                                                                                  |
| 9  | DynamoDBReconfigurePolicy                      | Gives permission to reconfigure a DynamoDB table.                                                                                 |
| 10 | SESSendBouncePolicy                            | Gives SendBounce permission to an Amazon Simple Email Service (Amazon SES) identity.                                              |
| 11 | ElasticsearchHttpPostPolicy                    | Gives POST permission to Amazon Elasticsearch Service.                                                                            |
| 12 | S3ReadPolicy                                   | Gives read-only permission to objects in an Amazon Simple Storage Service (Amazon S3) bucket.                                     |
| 13 | S3WritePolicy                                  | Gives write permission to objects in an Amazon S3 bucket.                                                                         |
| 14 | S3CrudPolicy                                   | Gives create, read, update, and delete permission to objects in an Amazon S3 bucket.                                              |
| 15 | AMIDescribePolicy                              | Gives permission to describe Amazon Machine Images (AMIs).                                                                        |
| 16 | CloudFormationDescribeStacksPolicy             | Gives permission to describe AWS CloudFormation stacks.                                                                           |
| 17 | RekognitionDetectOnlyPolicy                    | Gives permission to detect faces, labels, and text.                                                                               |
| 18 | RekognitionNoDataAccessPolicy                  | Gives permission to compare and detect faces and labels.                                                                          |
| 19 | RekognitionReadPolicy                          | Gives permission to list and search faces.                                                                                        |
| 20 | RekognitionWriteOnlyAccessPolicy               | Gives permission to create collection and index faces.                                                                            |
| 21 | SQSSendMessagePolicy                           | Gives permission to send message to an Amazon SQS queue.                                                                          |
| 22 | SNSPublishMessagePolicy                        | Gives permission to publish a message to an Amazon Simple Notification Service (Amazon SNS) topic.                                |
| 23 | VPCAccessPolicy                                | Gives access to create, delete, describe, and detach elastic network interfaces.                                                  |
| 24 | DynamoDBStreamReadPolicy                       | Gives permission to describe and read DynamoDB streams and records.                                                               |
| 25 | KinesisStreamReadPolicy                        | Gives permission to list and read an Amazon Kinesis stream.                                                                       |
| 26 | SESCrudPolicy                                  | Gives permission to send email and verify identity.                                                                               |
| 27 | SNSCrudPolicy                                  | Gives permission to create, publish, and subscribe to Amazon SNS topics.                                                          |
| 28 | KinesisCrudPolicy                              | Gives permission to create, publish, and delete an Amazon Kinesis stream.                                                         |
| 29 | KMSDecryptPolicy                               | Gives permission to decrypt with an AWS Key Management Service (AWS KMS) key.                                                     |
| 30 | KMSEncryptPolicy                               | Gives permission to encrypt with an AWS Key Management Service (AWS KMS) key.                                                     |
| 31 | PollyFullAccessPolicy                          | Gives full access permission to Amazon Polly lexicon resources.                                                                   |
| 32 | S3FullAccessPolicy                             | Gives full access permission to objects in an Amazon S3 bucket.                                                                   |
| 33 | CodePipelineLambdaExecutionPolicy              | Gives permission for a Lambda function invoked by CodePipeline to report the status of the job.                                   |
| 34 | ServerlessRepoReadWriteAccessPolicy            | Gives permission to create and list applications in the AWS Serverless Application Repository service.                            |
| 35 | EC2CopyImagePolicy                             | Gives permission to copy Amazon EC2 images.                                                                                       |
| 36 | AWSSecretsManagerRotationPolicy                | Gives permission to rotate a secret in AWS Secrets Manager.                                                                       |
| 37 | AWSSecretsManagerGetSecretValuePolicy          | Gives permission to get the secret value for the specified AWS Secrets Manager secret.                                            |
| 38 | CodePipelineReadOnlyPolicy                     | Gives read permission to get details about a CodePipeline pipeline.                                                               |
| 39 | CloudWatchDashboardPolicy                      | Gives permissions to put metrics to operate on CloudWatch dashboards.                                                             |
| 40 | RekognitionFacesManagementPolicy               | Gives permission to add, delete, and search faces in an Amazon Rekognition collection.                                            |
| 41 | RekognitionFacesPolicy                         | Gives permission to compare and detect faces and labels.                                                                          |
| 42 | RekognitionLabelsPolicy                        | Gives permission to detect object and moderation labels.                                                                          |
| 43 | DynamoDBBackupFullAccessPolicy                 | Gives read and write permission to DynamoDB on-demand backups for a table.                                                        |
| 44 | DynamoDBRestoreFromBackupPolicy                | Gives permission to restore a DynamoDB table from backup.                                                                         |
| 45 | ComprehendBasicAccessPolicy                    | Gives permission for detecting entities, key phrases, languages, and sentiments.                                                  |
| 46 | MobileAnalyticsWriteOnlyAccessPolicy           | Gives write-only permission to put event data for all application resources.                                                      |
| 47 | PinpointEndpointAccessPolicy                   | Gives permission to get and update endpoints for an Amazon Pinpoint application.                                                  |
| 48 | FirehoseWritePolicy                            | Gives permission to write to a Kinesis Data Firehose delivery stream.                                                             |
| 49 | FirehoseCrudPolicy                             | Gives permission to create, write, update, and delete a Kinesis Data Firehose delivery stream.                                    |
| 50 | EKSDescribePolicy                              | Gives permission to describe or list Amazon EKS clusters.                                                                         |
| 51 | CostExplorerReadOnlyPolicy                     | Gives read-only permission to the read-only Cost Explorer APIs for billing history.                                               |
| 52 | OrganizationsListAccountsPolicy                | Gives read-only permission to list child account names and IDs.                                                                   |
| 53 | SESBulkTemplatedCrudPolicy                     | Gives permission to send email, templated email, templated bulk emails and verify identity.                                       |
| 54 | SESEmailTemplateCrudPolicy                     | Gives permission to create, get, list, update and delete Amazon SES email templates.                                              |
| 55 | FilterLogEventsPolicy                          | Gives permission to filter CloudWatch Logs events from a specified log group.                                                     |
| 56 | SSMParameterReadPolicy                         | Gives permission to access a parameters from an Amazon EC2 Systems Manager (SSM) parameter store to load secrets in this account. |
| 57 | StepFunctionsExecutionPolicy                   | Gives permission to start a Step Functions state machine execution.                                                               |
| 58 | CodeCommitCrudPolicy                           | Gives permissions to create/read/update/delete objects within a specific CodeCommit repository.                                   |
| 59 | CodeCommitReadPolicy                           | Gives permissions to read objects within a specific CodeCommit repository.                                                        |
| 60 | AthenaQueryPolicy                              | Gives permissions to execute Athena queries.                                                                                      |
| 61 | TextractPolicy                                 | Gives full access to Amazon Textract.                                                                                             |
| 62 | TextractDetectAnalyzePolicy                    | Gives access to detect and analyze documents with Amazon Textract.                                                                |
| 63 | TextractGetResultPolicy                        | Gives access to get detected and analyzed documents from Amazon Textract.                                                         |
| 64 | EventBridgePutEventsPolicy                     | Gives permissions to send events to EventBridge.                                                                                  |
| 65 | ElasticMapReduceModifyInstanceFleetPolicy      | Gives permission to list details and modify capacities for instance fleets within a cluster.                                      |
| 66 | ElasticMapReduceSetTerminationProtectionPolicy | Gives permission to set termination protection for a cluster.                                                                     |
| 67 | ElasticMapReduceModifyInstanceGroupsPolicy     | Gives permission to list details and modify settings for instance groups within a cluster.                                        |
| 68 | ElasticMapReduceCancelStepsPolicy              | Gives permission to cancel a pending step or steps in a running cluster.                                                          |
| 69 | ElasticMapReduceTerminateJobFlowsPolicy        | Gives permission to shut down a cluster.                                                                                          |
| 70 | ElasticMapReduceAddJobFlowStepsPolicy          | Gives permission to add new steps to a running cluster.                                                                           |
| 71 | SageMakerCreateEndpointPolicy                  | Gives permission to create an endpoint in SageMaker.                                                                              |
| 72 | SageMakerCreateEndpointConfigPolicy            | Gives permission to create an endpoint configuration in SageMaker.                                                                |
| 73 | EcsRunTaskPolicy                               | Gives permission to start a new task for a task definition.                                                                       |
| 74 | EFSWriteAccessPolicy                           | Gives permission to mount an Amazon EFS file system with write access.                                                            |

