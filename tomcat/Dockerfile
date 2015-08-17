FROM ubuntu:12.04
MAINTAINER Crazyunix@163.com
ENV PEFRESHED_AT 2015-8-17

RUN apt-get update -qqy
RUN apt-get install wget -qqy
RUN apt-get install -qqy tomcat7 default-jdk

#VOLUME ["/data/tomcat/webapps/"]
#WORKDIR /data/tomcat/webapps/

ENV CATALINA_HOME /usr/share/tomcat7
ENV CATALINA_BASE /var/lib/tomcat7
ENV CATALINA_PID /var/run/tomcat7.pid
ENV CATALINA_SH /usr/share/tomcat7/bin/catalina.sh
ENV CATALINA_TMPDIR /tmp/tomcat7

RUN mkdir -p $CATALINA_TMPDIR

VOLUME ["/var/lib/tomcat7/webapps"]
EXPOSE 8080
ENTRYPOINT ["/usr/share/tomcat7/bin/catalina.sh","run"]
