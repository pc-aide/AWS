# CodeBuild Security

## Acronym
* VPC - Virtual Private Cloud
* SG - Security Group

## Doc

## Intro
* To access resources in your VPC, make sure you specify a VPC configuration for your CodeBuild
* Secrets in CodeBuild:
    * <ins>Don't store them as plaintext in environment variables</ins>
    * Instead...
        * Envrionment variables can reference parameter store parameters
        * Encrionment variables can reference secrets manager secrets
        
---

## Demo
* CodeBuild\Create build project
    * add configuration: 
      * VPC
      * Subnets
      * SGs
      * Environment variables
        * name: DB-PASSWORD
        * value: <reference\system manager\codebuild>
        * Type: Parameter (system manager\Parameter store - create new one for CodeBuild)
        
[<img src="https://i.imgur.com/TeSpSiK.png">](https://i.imgur.com/TeSpSiK.png)
[<img src="https://i.imgur.com/0s8v0pb.png">](https://i.imgur.com/0s8v0pb.png)
