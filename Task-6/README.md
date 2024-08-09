# Devops Task 6

## Description
Spring PetClinic Docker Setup

This repository contains a Dockerfile to build and run the Spring PetClinic application using Docker. The Dockerfile is configured to use Ubuntu 20.04 as the base image, install necessary dependencies, and build the application using Maven.

## Dockerfile Explanation

1. **Base Image**:
   - Uses the official Ubuntu 20.04 image.

2. **Environment Variables**:
   - Sets `DEBIAN_FRONTEND` to `noninteractive` to avoid interactive prompts during package installation.

3. **Dependencies**:
   - Updates the package list and installs necessary packages including `curl`, `git`, `unzip`, `xz-utils`, `zip`, `maven`, and `openjdk-17-jdk`.
   - Cleans up temporary files to reduce image size.

4. **Java Home**:
   - Sets the `JAVA_HOME` environment variable to point to the Java 17 installation directory.

5. **Application Setup**:
   - Clones the Spring PetClinic repository from GitHub.
   - Changes directory to the cloned repository.

6. **Permissions**:
   - Ensures that the Maven wrapper script (`mvnw`) has executable permissions.

7. **Build**:
   - Builds the Spring PetClinic application using Maven.

8. **Ports**:
   - Exposes port `8080` for the application.

9. **Entry Point**:
   - Runs the built JAR file using `java -jar` and directs logs to the terminal.

## Building the Docker Image

To build the Docker image, use the following command:

```bash
docker build -t spring-petclinic .
```

## Running the Docker Container
```bash
docker run -p 8080:8080 spring-petclinic
```

## Accessing the Application
```bash
http://localhost:8080
```
