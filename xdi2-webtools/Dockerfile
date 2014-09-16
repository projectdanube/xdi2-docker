FROM peacekeeper/xdi2:latest
MAINTAINER Markus Sabadello "markus@projectdanube.org"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get clean
RUN apt-get install -q -y wget && apt-get clean

RUN (wget -O /tmp/tomcat7.tar.gz http://mirror.cogentco.com/pub/apache/tomcat/tomcat-7/v7.0.55/bin/apache-tomcat-7.0.55.tar.gz && \
cd /opt && \
tar zxf /tmp/tomcat7.tar.gz && \
mv /opt/apache-tomcat* /opt/tomcat && \
rm /tmp/tomcat7.tar.gz)

ADD ./run.sh /usr/local/bin/run
RUN rm -rf /opt/tomcat/webapps/*
RUN cp /opt/xdi2/webtools/target/*.war /opt/tomcat/webapps/ROOT.war

EXPOSE 8080

CMD ["/bin/sh", "-e", "/usr/local/bin/run"]
