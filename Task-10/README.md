# Devops Task 10

## Description
This task involves setting up a petclinic application with a MySQL database using Docker and Docker Compose. The project provides Docker configurations for running the Spring Petclinic application with neginx container and copying the configuration files to the container of neginx.

## Project Structure
    - docker:
        - docker-compose.yml: Basic Docker Compose configuration for running the Spring Petclinic application.
    -nginx:
        - nginx.conf: Contains the configuration for neginx server.
    -petclinic:
        - Dockerfile: Contains the instructions to build the Docker image for the Spring Petclinic application.