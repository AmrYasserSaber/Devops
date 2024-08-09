# Devops Task 12

## Task Description 📄

Jenkins Setup and Spring PetClinic Deployment

🔅 Create container image that’s has Jenkins installed using Dockerfile

🔅 When we launch this image, it should automatically start Jenkins service in the container.

🔅 Create a free job in Jenkins by using the source code of the existing project of the task-10 (i.e. DevOpsTask10)

## Table of Contents 📑
 - overview
 - Jenkins Setup
 - configuration of the free job
 - running the job
 - conclusion

## Overview 📋
In this task, we have to create a container image that has Jenkins installed using Dockerfile. When we launch this image, it should automatically start the Jenkins service in the container. We have to create a free job in Jenkins by using the source code of the existing project of the task-10 (i.e. DevOpsTask10).

## Jenkins Setup 🛠️
1. Create a Dockerfile with the following code:
    ```Dockerfile
    FROM centos:latest
    RUN yum install wget -y
    RUN wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
    RUN rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
    RUN yum install java -y
    RUN yum install jenkins -y
    RUN java -jar /usr/lib/jenkins/jenkins.war
    ```
2. Build the Dockerfile using the following command:
    ```bash
    docker build -t jenkins:v1 .
    ```
3. Run the Dockerfile using the following command:
    ```bash
    docker run -it -p 8080:8080 jenkins:v1
    ```
4. Open the browser and type the following URL:
    ```bash
    http://localhost:8080
    ```
5. Copy the password from the following location:
    ```bash
    /var/lib/jenkins/secrets/initialAdminPassword
    ```
6. Paste the password in the Jenkins setup and click on continue.
7. Install the suggested plugins.
8. Create an admin user and click on save and finish.
9. Click on start using Jenkins.
10. Jenkins is successfully installed.
11. Create a new job by clicking on create new jobs.
12. Enter the job name and select the freestyle project.
    - add the following bash script in the build section:
    ```bash
    # Clone the repository
    git clone https://github.com/Mohamedzonkol/Dev-Ops-Tasks
    cd Task10
    
    # Build and run the Docker containers
    docker-compose up --build -d
    
    # Verify the containers are running
    docker ps
    ```
13. Click on OK.
14. Configure the job as per the requirement.
15. Click on apply and save.
16. The job is successfully created.
17. Click on build now to run the job.
18. The job is successfully run.
19. The job is successfully completed.
20. The Jenkins setup is successfully completed.