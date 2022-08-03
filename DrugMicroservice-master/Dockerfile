FROM maven:3.8.5-jdk-11 as builder
COPY .  /app
WORKDIR /app
RUN mvn install

FROM openjdk:11-jre
RUN mkdir /drugmicro
COPY --from=builder /app/target/*.jar  /drugmicro
WORKDIR /drugmicro
CMD ["java","-jar","drugservice-0.0.1-SNAPSHOT.jar"]
