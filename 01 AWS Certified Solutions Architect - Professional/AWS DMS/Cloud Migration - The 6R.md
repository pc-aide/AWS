# Cloud Migration - The 6R

## Acronym
* CRM - Customer Relationship Management
* SaaS - Software as a Service
* RDS - Relational Database Service  


## Doc
* [6 Strategies for Migrating Applications to the Cloud](https://aws.amazon.com/blogs/enterprise-strategy/6-strategies-for-migrating-applications-to-the-cloud/)

## Intro
1) **Rehosting**: "lift & shift"
  * Simple migrations by re-hosting on AWS (applications, databases, data...)
  * No cloud optimizations being done, application is migrated as is
  * Could save as much as 30% on cost
  * <ins>Example</ins> Migrate using AWS VM Import/Export,AWS Server Migration Service
2) Replatforming
  * <ins>Example</ins>: migrate your database to RDS
  * <ins>Example</ins>: migrate your application to Elastic Beanstalk (Java with Tomcat)
  * Not changing the core architecture, but leverage some cloud optimizations
3) **Repurchase**: "drop & shop"
  * Moving to a different product while moving to the cloud
  * Often you move to a SaaS patform
  * Expensive in the short term, but quick to deploy
  * <ins>Example</ins>: CRM to Salesforce.com, HR to Workday, CMS to Drupal
4) Refactoring / Re-architecting:
  * Reimagining how the application is architected using Cloud Native features
  * Driven by the need of the business to add features, scale, performance
  * <ins>Example</ins>: move an application to Serverless architectures, use AWS S3
5) Retire
  * Turn off things you don't need (maybe as a result of Re-architecting)
  * Helps with reducing the surface areas for attacks (more security)
  * Save cost, maybe up to 10% to 20%
  * Focus your attention on resources that must be maintained
6) Retain
  * Do nothing for now (for simplicity, cost reason, imprtance...)
  * It's still a decision to make in a Cloud Migration

### Diagram
[<img src="https://i.imgur.com/pB3b25H.png">](https://i.imgur.com/pB3b25H.png)
