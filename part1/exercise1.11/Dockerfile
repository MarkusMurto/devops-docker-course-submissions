FROM openjdk:8-jdk-slim-buster
EXPOSE 8080
WORKDIR /java-app

# cloning the spring project
RUN apt-get update && apt-get install -y git
RUN git clone --depth 1 --filter=blob:none --no-checkout https://github.com/docker-hy/material-applications.git
RUN cd material-applications && git checkout main -- spring-example-project

# building
RUN cd material-applications/spring-example-project && ./mvnw package

CMD ["java","-jar","material-applications/spring-example-project/target/docker-example-1.1.3.jar"]
