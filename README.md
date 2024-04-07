# Konzek Junior DevOps Assignment

## Objective
This project aims to streamline the deployment processes of a web application through the implementation of a DevOps approach.


## Requirements
- Git
- Docker
- Jenkins

## Installation Steps

### Step 1: GitHub Repository
1. Create a new GitHub repository for the project.
2. Push Dockerfile, index.html, Jenkinsfile-CI, and Jenkinsfile-CD files to the repository.

### Step 2: Setting Up Jenkins Server
1. Create a security group in AWS console with open ports for SSH (22), HTTP (80), and TCP (8080).
2. Launch an AWS EC2 instance with Ubuntu 20.04 using jenkins-server.sh userdata script.
3. Connect to the Jenkins server and create Dockerhub credentials.
4. Define the Jenkins server URL in the GitHub repository's GitHub webhook settings.

### Step 3: Creating the CI Pipeline
1. In the Jenkins console, create a pipeline named KONZEK_CI.
2. Enable the GitHub hook trigger for GITScm polling option in the pipeline's build triggers section to trigger the pipeline on push events.
3. In the pipeline's definition section, select the pipeline script from SCM option.
4. Enter the URL of the GitHub repository and set the script path to Jenkinsfile-CI.
5. The first build can be triggered manually, and subsequent builds will be triggered automatically upon repository updates.

#### The pipeline should be displayed in the console as follows

![Jenkins-CI](/Jenkins-CI.png)


### Step 4: Creating the CD Pipeline
1. In the Jenkins console, create a pipeline named KONZEK_CD.
2. In the pipeline's definition section, select the pipeline script from SCM option.
3. Enter the URL of the GitHub repository and set the script path to Jenkinsfile-CD.
4. After the CI pipeline has run successfully, we can trigger this pipeline to build.
5. Once built, the web application will be up and running.

#### The pipeline should be displayed in the console as follows

![Jenkins-CD](/Jenkins-CD.png)

#### The final appearance of the website should be like this

![Konzek](/Konzek.png)