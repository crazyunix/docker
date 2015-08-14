FROM ubuntu:12.04
MAINTAINER crazyunix "crazyunix@163.com"
ENV REFRESHED_AT 2015-08-10
RUN apt-get update
RUN qpt-get -y install nginx
RUN mkdir -p /var/www/html
#ADD xx.conf /etc/nginx/conf.d/
EXPOSE 80
CMD ["/usr/sbin/nginx"]
