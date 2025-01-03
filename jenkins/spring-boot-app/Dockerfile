# You can change this base image to anything else
# But make sure to use the correct version of Java
FROM adoptopenjdk/openjdk11:alpine-jre

# Simply the artifact path
ARG artifact=target/spring-boot-web.jar

WORKDIR /opt/app

COPY ${artifact} app.jar

# This should not be changed
ENTRYPOINT ["java","-jar","app.jar"]


#$ java -jar target/spring-boot-web.jar --server.port=8081
#$ java -jar target/spring-boot-web.jar 
# docker run -d -p 8010:8080 -t ultimate-cicd-pipeline:v1