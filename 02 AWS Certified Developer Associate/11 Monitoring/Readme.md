# Monitoring

## Acronym

## Doc

## Why Monitoring is Important
* We know how to deploy applications
    * Safely
    * Automatically
    * Using Infrastructure as Code
    * Leveraging the best AWS components
* Our applications are deployed, & our users don't care how we did it...
* Our users only care that the application is working
    * Application latency: will it increase over time?
    * Application outages: customer experience should not be degraded
    * Users contacting the IT department or complaining is not a good outcome
    * Troubleshooting & remediation
* Internal monitoring:
    * Can we prevent isssues before they happen?
    * Performance & Cost
    * Trends (scaling patterns)
    * Learning & Improvement
    
---

## Monitoring in AWS
* CloudWatch:
    * Metrics: Collect & track key metrics
    * Logs: Collect, monitor, analyze & store log files
    * Events: Send notifications when certain events happen in your AWS 
    * Alarms: React in real-time to metrics/ events
* AWS X-Ray:
    * Troubleshooting application performance & errors
    * Distributed tracing of microservices
* AWS CloudTrail:
    * Internal monitoring of API calls being made
    * Audit changes to AWS Resources by your users
