FROM gradle:7.6.1-jdk11 AS build

WORKDIR /app

COPY . /app

RUN gradle clean build --no-daemon

FROM openjdk:11-jre-slim

WORKDIR /app

COPY --from=build /app/build/libs/*.jar /app/leafy.jar

EXPOSE 8080
ENTRYPOINT ["java"]
CMD ["-jar", "leafy.jar"]
