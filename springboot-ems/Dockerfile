FROM maven:3.8.5-openjdk-17 AS build
COPY . .
RUN mvn clean package -DskipTests

FROM openjdk:24.0.1-jdk-slim
COPY --from=build /target/*.jar springbootfirst.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","springbootfirst.jar"]