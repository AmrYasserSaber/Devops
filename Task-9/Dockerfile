FROM ubuntu:22.04

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -y openjdk-17-jdk git maven curl && \
    apt-get clean

WORKDIR /app

RUN git clone https://github.com/dockersamples/spring-petclinic-docker.git

WORKDIR /app/spring-petclinic-docker

RUN chmod +x ./mvnw && ./mvnw package

EXPOSE 8080

ENV APP_VERSION="1.0.0"

RUN echo "Running Spring Petclinic version $APP_VERSION"

CMD ["java", "-jar", "target/spring-petclinic-2.7.0-SNAPSHOT.jar"]
