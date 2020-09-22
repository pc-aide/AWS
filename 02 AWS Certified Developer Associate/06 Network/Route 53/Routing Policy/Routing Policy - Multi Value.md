# Routing Policy - Multi Value

## Doc

## Acronym
* ELB - Elastic Load Balancing

## Introduction
* Use when routing traffic to multiple resources
* Want to associate a Route 53 health checks with records
* Up to 8 healthy records are returned for each Multi Value query
* Multi Value is not a substiture for having an ELB

### Table
| Name            | Type     | Value        | TTL | Set ID | Health Check |
| ----------------| -------- | ------------ | --- | ------ | ------------ |
| www.example.com | A Record | 192.0.2.0    | 60  | Web1   | A            |
| www.example.com | A Record | 198.51.100.2 | 60  | Web2   | B            |
| www.example.com | A Record | 203.0.113.2  | 60  | Web3   | C            |
