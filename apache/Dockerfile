# Simple Apache2 server running
FROM     ubuntu
MAINTAINER lynxbat@gmail.com

RUN apt-get update
RUN apt-get install -y apache2

RUN mkdir -p /var/apache/lock
RUN mkdir -p /var/apache/pid

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_LOCK_DIR /var/apache/lock 
ENV APACHE_PID_FILE /var/apache/pid/apache2.pid 

run echo 'ServerName localhost' >> /etc/apache2/apache2.conf

EXPOSE 80

ENTRYPOINT ["/usr/sbin/apache2"]
CMD ["-D", "FOREGROUND"]