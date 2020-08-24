FROM openjdk:11
#FROM maven:3.6.3

ADD ./ ./discoveryser

RUN ls -la

WORKDIR /discoveryser/target
RUN ls -la

ENTRYPOINT ["java","-jar","./discovery-service-0.0.1-SNAPSHOT.jar"]
EXPOSE 8761