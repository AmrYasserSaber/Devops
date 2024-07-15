# Use an official MySQL runtime as a parent image
FROM mysql:latest

# Environment variables
ENV MYSQL_ROOT_PASSWORD=root
ENV MYSQL_DATABASE=cred
ENV MYSQL_USER=cred
ENV MYSQL_PASSWORD=password

# Copy SQL script to initialize database (optional)
# COPY ./init.sql /docker-entrypoint-initdb.d/

# Expose MySQL default port
EXPOSE 3306
