# PHP5 Running
# For laravel with FTP Mongodb support 
FROM ubuntu:14.04
MAINTAINER Brooks Yang <brooksyang@outlook.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update 
RUN apt-get install -y vim wget curl zip git htop

RUN apt-get install -y apache2 
RUN apt-get -y install php5 libapache2-mod-php5
RUN apt-get -y install snmp php5-mysql php5-curl php5-gd php5-intl php-pear php5-imagick php5-imap php5-mcrypt php5-memcache  php5-pspell php5-recode php5-sqlite php5-tidy php5-xmlrpc php5-xsl php-mbstring php-gettext

RUN curl -sS https://getcomposer.org/installer | php
RUN mv composer.phar /usr/local/bin/composer
# RUN composer config -g repo.packagist composer http://packagist.phpcomposer.com


ADD 000-default.conf /etc/apache2/sites-enabled/000-default.conf

RUN a2enmod rewrite

EXPOSE 80

CMD /usr/sbin/apache2ctl -D FOREGROUND
 

