# §01 - Intro AWS Cloud API

## Questins
1. Which of the following is typically used to sign API calls to AWS service?
    * A. CMK
    * B. AWS access key
    * C. IAM user name & pwd
    * D. Account number
2. When you make API calls to AWS services, for most services those requests are directed at a specific endpoint that corresponds to which of the following?
    * A. AWS facility
    * B. AWS AZ
    * C. AWS Region
    * D. AWS edge location
3. When you're configuring a local development machine to make AWS API calls, which of the following is the simplest secure method of obtaining an API credential?
    * A. Create an IAM user, assign permissions by adding the user to an IAM group which IAM policies attached, & generate an access key for programmatic access
    * B. Sign in with your email & password, & visit My Security Credentials to generate an access key
    * C. Generate logn-term credentials for a built-in IAM role
    * D. Use your existing user name & password by configuring local environment variables
4. You have a large number of employee, & each employee already has an identity in an external directory. How might you manage AWS API credentials for each employee so that they can interact with AWS for short-term session?
    * A. Create an IAM user & credentials fro each member of your organization
    * B. Share a single password through a file stored in an encrypted Amazon S3 bucket
    * C. Define a set of IAM roles, & establish a trust relationship between your directory & AWS
    * D. Cofigure the AWS Key Management Service (AWS KMS) to store credentials for each user
5. You have a tema member who needs access to write records to an existing Amazon DynamoDB table within your account. How might you grant write permission to this specific table & only this table?
    * A. Write a custom IAM policy that specifies the table as the resource, & attach that policy to the IAM user for the team member
    * B. Attach the DynamoDBFullAccess managed policy to the IAM role used by the team member
    * C. Delete the table & recreate it. Permissions are set when the DynamoDB table is created
    * D. Create a new user within DynamoDB, & assign table permissions
6. You created a Moviess DynamoDB table in the AWS Managment Console, but when you try to list your DynamoDB tables by using the Java SDK, you do not see this table. Why?
    * A. DynamoDB table created in the AWS Managment Console are not accessible form the API
    * B. Your SDK may be listing your resources from a different AWS Region in which the table does not exist
    * C. The security group applied to the Movies table is keeping it hidden
    * D. Listing tables is supportd only in C# & not in the Java SDK
7. You make an API request to describe voices offered by Amazon Polly by using the AWS CLI, & you receive the following error message: https://polly.us-east-1a.amazonaws.com/v1/voices<br/>What ent wrong?
   * A. Your API credentials have been rejected
   * B. You have incorrectly configured the AWS Region for your API call
   * C. Amazon Polly does not offer a feature to describe the list of available voices
   * D. Amazon Polly is not accessible from the AWS CLI because it's only in the AWS SDK
8. To what resource does this IAM policy grant access, & for which actions?
````json
{
   "Version": "2012-10-17",
   "Statement": {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::example_bucket"
   }
}
````
   * A. The policy grants full acces to read to objects in the Amazon S3 bucket
   * B. The policy grants the bolder the permission to list the content of the Amazon S3 bucket called example_bucket
   * C. Nothing. The policy was valid only until October 17,212 (2012-10-17), & is now expired
   * D. The policy grants the user access to list hte content of all Amazon S3 buckets within the current account
9.  When an IAM user makes an API call, that user's logn-term credentials are valid in which context?
    * A. Only in the AWS Region in which their identity resides
    * B. Only inthe AZ in which their idenity resides
    * C. Only in the edge location in which their idenity resides
    * D. Across multiple AWS Regions
10. When you use identity federation to assume a role, where are the credentials you use to make AWS API calls generated?
    * A. Access key ID & secret access key are generated locally on the client
    * B. The AWS STS gnerates the access key ID, secret access key, & session token
    * C. The AWS KMS geneates a CMK
    * D. Your SAML identity provider generates the access key ID, secret access key, & session token
11. You have an open-premises application that needs to sample data from all your Amazon DynamoDB tables. You have  defined an IAM user for your application called TableAuditor. How can you give the TableAuditor user read access to new DynamoDB tables as soon they are created in your account?
    * A. Define a custom IAM policy that lists each DynamoDB table. Revoke the access key, & issue a new access key for TableAuditor when tables are created.
    * B. Create an IAM user & attach one custom IAM policy per AWS Region that has DynamoDB tables.
    * C. Add the TableAuditor user to the IAM role DynamoDBReadOnlyAccess
    * D. Attach the AWS managed IAM policy AmaonDynamoDBReadOnlyAccess to the TableAuditor user
12. The principals who have access to assume an IAM role are defined in which document?
    * A. IAM access policy
    * B. IAM trust policy
    * C. MS gran token
    * D. AWS credentials file
13. A new developer has joined your small team. You would loke to help you team member set up a development computer for access to the team account quickly & securely. How do your proceed?
    * A. Generate an access key based on your IAM user, & share it with your tem member.
    * B. Create a new directory with AWS Directory Service, & assign permissions in the AWS KMS
    * C. Create an IAM user, add it to an IAM group that has the appropriate permissions, & generate a long-term access key
    * D. Create a new IAM role for this team member, assign permissions to the role, & generate a long-term access key
14. You have been working with the Amazon Polly service in your application by using the Python SDK for Linux. You are bulding a second application in C#, & you would loke to run that application on a separate Windows Server with .NET. How can you proceed?
    * A. Migrate all your code for all applications to C#, & modify your account to a Windows account
    * B. Go to the Amazon Polly service, & change the supported languages to include .NET.
    * C. Install the AWS SDK for .NET on your Windows Server, & leave your existing application unchanged
    * D. Implement aproxy service that accepts your API requests, & translate them to Python
15. You are a Virginia-based company, & you have been asked to implement a custom application exclusively for customers in Australia. This application has no dependencies on any of your existing applications. What is a method your use to keep the customer latency to this new application low?
    * A. Set up an AWS DX between your on-premises environment & US East (N Virginia), & host he application form your own data center in Virginia
    * B. Create all resources for this application in the Asia Pacific (Sydney) Region, & manage them from your current account
    * C. Deploy the application to the US East (N Virginia) Region, & select Amazon EC2 instances with enhanced networking
    * D. It does not matter which region you select, because all resources are automatically replicated globally
*[Answers]()
