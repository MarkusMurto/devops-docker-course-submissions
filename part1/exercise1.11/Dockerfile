FROM openjdk:8-jdk-slim-buster
EXPOSE 8080
WORKDIR /java-app

# copy the project to the image
COPY . .

# building
RUN ./mvnw package

CMD ["java","-jar","./target/docker-example-1.1.3.jar"]
