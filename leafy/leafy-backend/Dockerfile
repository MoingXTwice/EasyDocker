FROM gradle:7.6.1-jdk11 AS build

WORKDIR /app

COPY build.gradle settings.gradle ./

RUN gradle dependencies --no-daemon

COPY . /app

RUN gradle clean build --no-daemon

FROM openjdk:11-jre-slim

WORKDIR /app

COPY --from=build /app/build/libs/Leafy-0.0.1-SNAPSHOT.jar /app/leafy.jar

EXPOSE 8080
EXPOSE 5005

ENTRYPOINT ["java"]
CMD ["-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=*:5005", "-jar", "leafy.jar"]
