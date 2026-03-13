FROM maven:3.9.9-eclipse-temurin-21-jammy AS BUILD_IMAGE
RUN git clone https://github.com/baljeet422/Containerized-web-App-using-Docker.git
RUN cd Containerized-web-App-using-Docker && mvn install


FROM tomcat:10-jdk21
LABEL "Project"="Vpro"
LABEL "Author"="Baljeet"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY  --from=BUILD_IMAGE Containerized-web-App-using-Docker/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD ["catalina.sh","run"]