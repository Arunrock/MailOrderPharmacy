FROM maven:3.8.5-jdk-11 as builder
COPY .  /app
WORKDIR /app
RUN mvn install

FROM openjdk:11-jre
RUN mkdir /jdbc
COPY --from=builder /app/target/*.jar  /jdbc
WORKDIR /jdbc
CMD ["java","-jar","spring-boot-jdbc-0.0.1-SNAPSHOT.jar"]