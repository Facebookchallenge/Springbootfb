FROM maven:3.8.5-openjdk-17 AS build

WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

FROM openjdk:17.0.1-jdk-slim
COPY --from=build /app/target/Facebook-0.0.1-SNAPSHOT.jar Facebook.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "Facebook.jar"]



