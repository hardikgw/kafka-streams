####
# This Dockerfile is used in order to build a container that runs the Quarkus application in JVM mode in OpenJDK Container
#
# Before building the container image run:
#
# ./mvnw package -Dquarkus.package.uber-jar=true
#
# Then, build the image with:
#
# docker build -f src/main/docker/Dockerfile -t cithub/kafka-streams .
#
# Then run the container using:
#
# docker run -i --rm -p 8080:8080 cithub/kafka-streams
#
###

FROM openjdk:11-jre-slim
COPY target/*-runner.jar /app/app.jar
WORKDIR /app
RUN sh -c 'touch app.jar'
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/app/app.jar"]