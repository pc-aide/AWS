# EB - Single Docker

## Acronym
* EB - Elastic Beanstalk
* ECS - Elastic Container Service

## Doc

## Intro
* Run your application as a single docker container
* Either provide:
    * **DockerFile**: EB will build & run the Docker container
    * **DockerRun.aws.json (v1)**: Describe where *already built* Docker image is
      * Image
      * Ports
      * Volumes
      * Logging
      * Etc...
* Beanstalk in Single Docker Container <ins>does not use ECS</ins>
