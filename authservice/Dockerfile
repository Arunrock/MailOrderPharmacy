FROM maven:3.8.5-jdk-11 as builder
COPY .  /app
WORKDIR /app
RUN mvn install

FROM openjdk:11-jre
RUN mkdir /Authorization
COPY --from=builder /app/target/*.jar  /Authorization
WORKDIR /Authorization
CMD ["java","-jar","Authorization-0.0.1-SNAPSHOT.jar"]Authorization
