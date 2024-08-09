# Devops Task 9

## Description

This project provides Docker configurations for running the Spring Petclinic application with different database setups using Docker Compose. It includes configurations for development, production, and a basic Docker setup.

## Project Structure

- **Dockerfile**: Contains the instructions to build the Docker image for the Spring Petclinic application.
- **docker-compose.yml**: Basic Docker Compose configuration for running the Spring Petclinic application.
- **docker-compose.prod.yml**: Docker Compose configuration for production environment with PostgreSQL.
- **docker-compose.dev.yml**: Docker Compose configuration for development environment with MySQL.

## Dockerfile

The `Dockerfile` builds a Docker image for the Spring Petclinic application with the following steps:
1. **Base Image**: Uses `ubuntu:22.04`.
2. **Install Dependencies**: Installs `openjdk-17-jdk`, `git`, `maven`, and `curl`.
3. **Clone Repository**: Clones the Spring Petclinic repository.
4. **Build Application**: Packages the application using Maven.
5. **Expose Port**: Exposes port `8080`.
6. **Set Environment Variable**: Sets the application version.
7. **Run Application**: Executes the Spring Petclinic JAR file.

## Docker Compose Configurations

### Basic Setup

- **File**: `docker-compose.yml`
- **Description**: Provides a basic setup to run the Spring Petclinic application.

### Production Setup

- **File**: `docker-compose.prod.yml`
- **Description**: Provides a production-ready configuration with PostgreSQL.
- **Environment Variables**:
  - `SPRING_PROFILES_ACTIVE`: Set to `postgres` to use PostgreSQL.
  - `POSTGRES_URL`: JDBC URL for PostgreSQL.
  - `POSTGRES_USER`: PostgreSQL username.
  - `POSTGRES_PASS`: PostgreSQL password.

### Development Setup

- **File**: `docker-compose.dev.yml`
- **Description**: Provides a development configuration with MySQL.
- **Environment Variables**:
  - `SPRING_PROFILES_ACTIVE`: Set to `mysql` to use MySQL.
  - `MYSQL_URL`: JDBC URL for MySQL.
  - `MYSQL_USER`: MySQL username.
  - `MYSQL_PASS`: MySQL password.

## Getting Started

1. **Build Docker Image**: 
   ```bash
   docker build -t spring-petclinic .
    ```
2. **Run def Setup**: 
   ```bash
   docker compose -f docker-compose.yml -f docker-compose.dev.yml up
    ```
3. **Run prod Setup**: 
   ```bash
   docker compose -f docker-compose.yml -f docker-compose.prod.yml up
    ```
4. **Access Application**:
    - Open a web browser and go to `http://localhost:8080` to access the Spring Petclinic application.
