FROM maven:3.8.5-jdk-11 as builder
COPY .  /app
WORKDIR /app
RUN mvn install

FROM openjdk:11-jre
RUN mkdir /Refillmicro
COPY --from=builder /app/target/*.jar  /Refillmicro
WORKDIR /Refillmicro
CMD ["java","-jar","RefillMicroService-0.0.1-SNAPSHOT.jar"]
