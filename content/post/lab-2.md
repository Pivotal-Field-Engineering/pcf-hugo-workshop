+++
Categories = ["lab"]
Tags = ["docker","cloudfoundry"]
date = "2016-03-15T14:54:22-04:00"
title = "Lab 2"
weight = 3

+++


Run Docker Containers in Cloud Foundry
-

Goals
--

To deploy and configure a spring boot app in Docker container and run it in Cloud Foundry.

<!--more-->





# How to run a Spring Boot App in a Docker Container in Cloud Foundry

This is the repo for a Spring Boot app in Docker
[Original Repo](https://spring.io/guides/gs/spring-boot-docker/#scratch)

The Spring boot app is deployed in Cloud Foundry as a Docker Container

# 5-Steps

1. Clone the Repo
--
   ```bash
     git clone https://github.com/rjain-pivotal/spring-boot-docker-cf.git
   ```
2. Build it and Run it locally
--
   If using Maven

   ```bash
     mvn package && java -jar target/gs-spring-boot-docker-0.1.0.jar
   ```

   If using Gradle

   ```
     ./gradlew build && java -jar build/libs/gs-spring-boot-docker-0.1.0.jar
   ```

3. Containerize it
--
   If using Maven

   ```bash
      $ mvn package docker:build
      # Push the Image to Docker
      $ docker push <docker-user>/gs-spring-boot-docker
   ```

   If using Gradle

   ```bash
      $ ./gradlew build buildDocker
   ```

4. Check and Run
--
   ```bash
      $docker images
      # Get the Docker Machine VM IP if running on a MAC
      $docker-machine env default (Get the Machine IP)
      $docker run -p 8080:8080 -t rjain15/gs-spring-boot-docker
      $curl http://192.168.99.100:8080  (Use the Machine IP)
   ```

5. Run it in Cloud Foundry
--
   ```bash
      $cf push -o <docker-user>/gs-spring-boot-docker -c "java -Djava.security.egd=file:/dev/./urandom -jar /app.jar"
   ```
