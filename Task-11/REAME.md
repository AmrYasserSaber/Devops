# Devops Task 11

# Description
this task involves trying out amazing features of docker-compose. The project provides Docker configurations for running the Spring Petclinic application with different database setups using Docker Compose. with some amazing features of docker-compose like volumes, networks, and environment variables.

# Project Structure
     ** fastapi **:
        - Dockerfile: Contains the instructions to build the Docker image for the FastAPI application.
        - app: Contains the FastAPI application code.
    - ** flaskapi **:
        - Dockerfile: Contains the instructions to build the Docker image for the Flask API application.
        - app: Contains the Flask API application code.
    - ** minncraft **:
        - Dockerfile: Contains the instructions to build the Docker image for the Minecraft server.
        - server.properties: Contains the configuration for the Minecraft server.
    - ** postgresql-pgadmin **:
        - Dockerfile: Contains the instructions to build the Docker image for PostgreSQL and pgAdmin.
        - pgadmin: Contains the pgAdmin configuration files.
    - ** react-express-mongodb **:
        - Dockerfile: Contains the instructions to build the Docker image for the React, Express, and MongoDB application.
        - client: Contains the React application code.
        - server: Contains the Express application code.