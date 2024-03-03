FROM openjdk:11 AS BUILS_IMAGE
RUN apt-get update && apt-get install maven -y
RUN git clone https://github.com/devopshydclub/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install

FROM tomcat:9-jre11
LABEL "project"="vprofile"
LABEL "Auther"="Hamza Gul Khan"
RUN rm -rf /usr/local/tomcat/webapp/*
copy --from=BUILS_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapp/ROOT.war

EXPOSE 8080
CMD ["catalina.sh","run"]
