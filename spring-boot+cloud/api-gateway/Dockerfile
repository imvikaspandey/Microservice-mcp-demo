FROM openjdk:11
#FROM maven:3.6.3

ADD ./ ./api-gateway

RUN ls -la

WORKDIR /api-gateway/target
RUN ls -la

ENTRYPOINT ["java","-jar","./api-gateway-0.0.1-SNAPSHOT.jar"]
EXPOSE 8080