FROM openjdk:11 AS Build_Image
RUN apt update && apt install maven -y
RUN git clone https://github.com/faisalhkazi/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install

FROM tomcat:9.0-jre11
LABEL "Project"="vprofile"
LABEL "Author"="Imran"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=Build_Image vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]