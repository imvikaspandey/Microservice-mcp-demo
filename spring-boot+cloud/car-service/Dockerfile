FROM openjdk:11
#FROM maven:3.6.3

ADD ./ ./carser

RUN ls -la

WORKDIR /carser/target
RUN ls -la

ENTRYPOINT ["java","-jar","./car-service-0.0.1-SNAPSHOT.jar"]
EXPOSE 8090