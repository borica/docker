FROM debian:latest

#Environment variables
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_PID_FILE /var/run/apache2/apache2.pid
ENV APACHE_SERVER_NAME localhost

#Update apt and grab packages
RUN apt-get update -y
RUN apt-get install -y vim 
RUN apt-get install -y apache2
RUN apt-get install -y php

#Copy apache-conf
COPY apache-conf /etc/apache2/apache2.conf

#Expose container port
EXPOSE 80

#Launch apache and hook it at -IT
CMD ["/usr/sbin/apache2ctl", "-DFOREGROUND"]