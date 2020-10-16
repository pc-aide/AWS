# Quiz 20 - API Gateway

## Questions
1) To make a serverless API, I should integrate API Gateway with
    * EC2
    * ELB
    * Lambda
* [Answer](https://i.imgur.com/4ivFetN.png)
2) In order to redirect my API Gateway stage to the correct AWS Lambda alias, I should use
    * Deployment stages canary
    * Stage Variables
    * X-Ray integration
    * HTTP endpoints
* [Answer](https://i.imgur.com/9x0uzND.png)
3) I want to test a whole new API (v2) but I'm worried about shifting all my traffic to it. The recommend way is to
    * Create a whole new stage & use Route 54 to balance between my two stages using a CNAME
    * Create a canary release in my first environment
    * Update all my lambda functions to use Aliases
* [Answer](https://i.imgur.com/RXVALkn.png)
4) You would like to mask fields in the output data sent back by your Lambda function
    * Use a custom authorizer
    * Use mapping templates
    * Use a Cognito mask
* [Answer](https://i.imgur.com/w0WNW5S.png)
5) Which specification allows you to import and export your API?
    * gRPC
    * SOAP
    * Swagger
* [Answer](https://i.imgur.com/xUo7PS5.png)
6) Your API is getting hit with the same GET request over and over. Your lambda function is overloaded and your bill starts to substantially increase. The GET response returns the same payload and changes only daily. What should you do?
    * Enable mock response
    * Integrate API Gateway with ElastiCache
    * Enable Stage Cache
* [Answer](https://i.imgur.com/2Wy2BQ6.png)
7) How can you invalidate the cache client side?
    * Use stage variables
    * Pass an URL paramter 
    * Pass the header Cache-Control:max-age=0
* [Answer](https://i.imgur.com/IYyRxlR.png)
8) You would like to analyze the full picture of the latency of your API calls. You should use 
    * CW logs
    * CW detailed metrics
    * X-Ray
* [Answer](https://i.imgur.com/Gz6kD6Z.png)
9) You would like to use your API from another domain. You need to
    * Deploy to a new stage
    * Enable CORS
    * Add a stage variable
* [Answer](https://i.imgur.com/XU5J3pV.png)
10) You would like to validate 3rd party tokens provided in the Bearer Header for authentication. You need
    * IAM Security with API Gateway
    * Lambda Authorizer with API Gateway
    * Cognito with API Gateway
* [Answer](https://i.imgur.com/tEz1MYN.png)
11) You would like to provide a Facebook login before your users call your API hosted by API Gateway. You need seamlessly authentication integration, you will use
    * Cognito Sync
    * DynamoDB user tables with Lambda Authorizer
    * Cognito User Pools
    * Cognito Federated Identity Pools
* [Answer](https://i.imgur.com/AFYAVfe.png)
12) You have created an API key and a Usage plan, yet using the API key doesn't work. What should be done?
    * You must create a deployment
    * You must change the authorizers
    * You must associate the API key with the usage plan
* [Answer](https://i.imgur.com/cYcg2Ds.png)
13) Which metric can help you analyze integration & timeout issues between a Lambda function and API Gateway?
    * CacheHitCount
    * IntegrationLatency
    * CacheMissCount
    * Count
* [Answer](https://i.imgur.com/4PzP0vX.png)
14) Which statement is true?
    * API Gateway supports real-time APIs through WebSocket
    * API Gateway does not support real-time APIs through WebSocket
* [Answer](https://i.imgur.com/xhHdz00.png)
