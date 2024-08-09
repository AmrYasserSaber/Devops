# Devops Task 8


# Spring Petclinic Docker Setup

This project sets up the Spring Petclinic application with a MySQL database using Docker and Docker Compose. Below are instructions to get started.

## Overview

The setup includes:
- **Spring Petclinic Application**: Built from source using a Dockerfile.
- **MySQL Database**: Managed by Docker Compose.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed
- [Docker Compose](https://docs.docker.com/compose/install/) installed

## Directory Structure

- `Dockerfile`: Defines the build instructions for the Spring Petclinic application.
- `docker-compose.yml`: Defines the services for running the Petclinic application and MySQL database.

## Configuration

### Dockerfile

The Dockerfile is used to build the Spring Petclinic application image. It:
- Uses Ubuntu 20.04 as the base image
- Installs necessary dependencies and Java 17
- Clones the Spring Petclinic repository and builds the application

### docker-compose.yml

The `docker-compose.yml` file sets up two services:
- **petclinic**: The Spring Petclinic application
  - **Build Context**: `../eighth-task`
  - **Ports**: Maps host port `8080` to container port `8080`
  - **Environment Variables**: Configures the application to use MySQL
  - **Depends On**: Waits for the MySQL database service to start

- **db**: The MySQL database
  - **Image**: Uses `mysql:8.4`
  - **Ports**: Exposes port `3306`
  - **Volumes**: Mounts a local configuration directory

## Getting Started

1. **Clone the Repository**:
   ```bash
   docker-compose up
   ```

