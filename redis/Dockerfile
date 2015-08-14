FROM ubuntu:12.04
MAINTAINER crazyunix "crazyunix@163.com"
ENV PEFRESHED_AT 2015-08-14
RUN apt-get update
RUN apt-get install redis-server
EXPOSE 6379
ENTRYPOINT ["/usr/bin/redis-server"]
CMD []
