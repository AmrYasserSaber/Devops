# Use the official Ubuntu 20.04 base image
FROM ubuntu:20.04

# Set environment variable to noninteractive to avoid prompts
ENV DEBIAN_FRONTEND=noninteractive

# Install dependencies and Java 17 in a single RUN command
RUN apt-get update && apt-get install -y \
    curl \
    git \
    unzip \
    xz-utils \
    zip \
    maven \
    openjdk-17-jdk \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Set JAVA_HOME
ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64

# Clone the repository and build the application
WORKDIR /
RUN git clone https://github.com/spring-projects/spring-petclinic.git
WORKDIR /spring-petclinic

# Ensure maven wrapper has executable permissions
RUN chmod +x ./mvnw

# Build the project
RUN ./mvnw package

# Expose the port
EXPOSE 8080

# Set the entry point to run the JAR file and show logs on the terminal
CMD ["sh", "-c", "java -jar target/*.jar > /proc/1/fd/1 2>&1"]
