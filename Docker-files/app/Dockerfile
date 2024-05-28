# Later on update to the latest version openjdk:17
FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/alain-github120/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install

LABEL "Project"="vprofile"
LABEL "Author"="alain"


# Later on update to the latest version tomcat:10.1.24-jre17
FROM tomcat:9-jdk11     
RUN rm -rf /usr/local/tomcat/webapp/*
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapp/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]

