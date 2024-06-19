# CI/CD Pipeline with GitLabCI for Spring Boot REST API
This repository contains a  Spring Boot REST API project that is integrated with GitLabCI for Continuous Integration and Continuous Deployment. <br>
The repository (https://gitlab.com/adnanedrief/gitlab-ci-rest-api-springboot) contains the source code for the REST API and a Dockerfile to package the application as a Docker image.

## Prerequisites
- Java 17
- Maven
- Docker
- GitLab account

## Pipeline Overview
The pipeline consists of two stages: **build** and **deploy**.

### Build
In the **build** stage, the code is compiled using Maven and a JAR file is produced as an artifact.

### Deploy
In the **deploy** stage, the Docker image is built and pushed to the GitLab Container Registry.

## GitLabCI Configuration
- The **.gitlab-ci.yml** file contains the configuration for the pipeline. The configuration file defines the different stages in the pipeline, the jobs to be executed in each stage, and the Docker images to be used for each job.

- The build job is responsible for compiling the code and generating the jar file. The deploy job is responsible for building the Docker image and pushing it to GitLab.

- The pipeline uses two Docker images: maven:latest for the build job and docker:latest for the deploy job. The docker:dind service is used to enable Docker inside the Docker container used by the deploy job.

- The artifacts produced by the build job are stored in the target directory, which is defined in the artifacts section of the job. The deploy job retrieves the jar file from the artifacts and uses it to build the Docker image.

## Demo 
### Pipelines

<img src="https://i.ibb.co/CbyHVFY/pipelines.png">

### Build stage

<img src="https://i.ibb.co/mCqjysj/build-job.png">

### Deploy stage

<img src="https://i.ibb.co/pr2J2YP/deploy-job.png">

### Success pipeline

<img src="https://i.ibb.co/8Bz97YN/success-pipelines-2.png">

<img src="https://i.ibb.co/0jX3jKB/success-pipelines.png">
