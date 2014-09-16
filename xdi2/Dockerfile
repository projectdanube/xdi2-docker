FROM debian:wheezy
MAINTAINER Markus Sabadello "markus@projectdanube.org"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get clean
RUN apt-get install -q -y openjdk-7-jre-headless openjdk-7-jdk maven && apt-get clean

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64/
ENV PATH $JAVA_HOME/bin:$PATH

ADD . /opt/xdi2
WORKDIR /opt/xdi2

RUN mvn clean install package -DskipTests
