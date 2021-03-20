# 1.11: Spring

Commands:
```
$ git clone --depth 1 https://github.com/docker-hy/material-applications.git

$ cd material-applications/spring-example-project
```

Dockerfile:
```
FROM openjdk:8-jdk-slim-buster
EXPOSE 8080
WORKDIR /java-app

# copy the project to the image
COPY . .

# building
RUN ./mvnw package

CMD ["java","-jar","./target/docker-example-1.1.3.jar"]
```

Commands:
```
$ docker build . -t spring-example-project

$ docker run -it -p 80:8080 spring-example-project:latest
```

