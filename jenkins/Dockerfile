FROM ubuntu:14.04
MAINTAINER crazyunix@163.com
ENV PEFRESHED_AT 2015-08-14

RUN apt-get update -qq && apt-get install -qqy curl
RUN curl https://get.docker.io/gpg | apt-key add -
RUN echo ded http://get.docker.io/ubutu docker main > /etc/apt/souces.list.d/docker.list
RUN apt-get update -qq && apt-get install -qqy iptables cacertificates lxc openjdk-6-jdk git-core ldx-docker

ENV JENKENS_HOME /opt/jenkins/data
ENV JENKINS_MIRROR http://mirrors.jenkins-ci.org

RUN mkdir -p $JENKENS_HOME/plugins
RUN curl -sf -o /opt/jenkins/jenkins.war -L $JENKINS_MIRROR/war-stable/latest/jenkins.war
RUN for plugin in chuckorris greenballs scm-api git-client git ws-cleanup ;\
	do curl -sf -o $JENKENS_HOME/plugins/${plugin}.hpi \
	-L $JENKENS_MIRROR/plugins/${plugin}/latest/${plugin}.hpi; done

ADD ./dockerjenkins.sh /usr/local/bin/dockerjenkins.sh
RUN chmod +x /usr/local/bin/dockerjenkins.sh

VOLUME /var/lib/docker

EXPOSE 8080

ENTRYPOINT ["/usr/local/bin/dockerjenkins.sh"]

