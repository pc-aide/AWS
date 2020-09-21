# Health Checks

## Acronym

## Doc

## Introduction
* Have X health checks failed => unhealthy (default 3)
* After X health checks passed => health (default 3)
* Default health check interval: 30s (can set to 10s - higher cost)
* About 15 health checkers will check the endpoint health
* => one request every 2s on average
