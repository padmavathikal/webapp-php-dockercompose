FROM php:7.3-apache

#Install git and MySQL extensions for PHP

RUN apt-get update && apt-get install -y git
RUN docker-php-ext-install pdo pdo_mysql mysqli
RUN a2enmod rewrite

RUN apt-get update && apt-get install -y python python3-pip


RUN python3 -m pip install flask

#RUN python3 -m pip python-mysqldb

RUN python3 -m pip install flask-mysql


COPY app.py /opt/

ENTRYPOINT FLASK_APP=/opt/app.py flask run 

#COPY src /var/www/html/
EXPOSE 80/tcp
EXPOSE 443/tcp