# Devops Task 5

## Description

Spring pet clinic is a sample application that demonstrates the use of Spring Boot, Spring MVC, and Spring Data JPA.
This document outlines the steps to deploy the Spring pet clinic application on an Ubuntu server using Nginx as a
reverse proxy and SSL encryption using Let's Encrypt.
For git task I will only run it on my local machine and provide the output of the commands.

## Steps

clone the repository

```bash
git clone https://github.com/spring-projects/spring-petclinic
```

Change directory to the cloned repository

```bash
cd spring-petclinic
```
install java 17 or higher

```bash
sudo apt install openjdk-17-jdk
```

Build the project

```bash
./mvnw package
```

Run the application

```bash
java -jar target/*.jar
```

Open a web browser and navigate to `http://localhost:8080` to access the Spring pet clinic application.