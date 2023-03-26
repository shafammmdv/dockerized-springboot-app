FROM gradle:jdk17-focal AS build
WORKDIR "/home/app"
MAINTAINER Emin Mammadov
ADD . .
COPY gradle/ gradle
COPY gradlew build.gradle ./
RUN ./gradlew clean build


FROM openjdk:17
WORKDIR "/home/app"
ARG JAR_FILE=/home/app/build/libs/dockerized-app-2-0.0.1.jar
EXPOSE 8080
COPY --from=build ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","app.jar"]