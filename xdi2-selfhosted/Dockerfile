FROM projectdanube/xdi2:latest
MAINTAINER Markus Sabadello "markus@projectdanube.org"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get clean
RUN apt-get install -q -y wget && apt-get clean

RUN (wget -O /tmp/tomcat7.tar.gz http://www.eu.apache.org/dist/tomcat/tomcat-7/v7.0.57/bin/apache-tomcat-7.0.57.tar.gz && \
cd /opt && \
tar zxf /tmp/tomcat7.tar.gz && \
mv /opt/apache-tomcat* /opt/tomcat && \
rm /tmp/tomcat7.tar.gz)

RUN mkdir /opt/xdi2-selfhosted
RUN git clone https://github.com/projectdanube/xdi2-selfhosted.git /opt/xdi2-selfhosted
WORKDIR /opt/xdi2-selfhosted

RUN mvn clean install package -DskipTests

ADD ./run.sh /usr/local/bin/run
ADD ./xdi2-selfhosted.properties /etc/xdi2/xdi2-selfhosted.properties
RUN rm -rf /opt/tomcat/webapps/*
RUN cp /opt/xdi2-selfhosted/target/*.war /opt/tomcat/webapps/ROOT.war

EXPOSE 8080

CMD ["/bin/sh", "-e", "/usr/local/bin/run"]
