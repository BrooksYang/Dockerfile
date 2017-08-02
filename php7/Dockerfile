# PHP7 Running
# For laravel with FTP Mongodb support 
FROM ubuntu:16.04
MAINTAINER Brooks Yang <brooksyang@outlook.com>

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update 
RUN apt-get install -y vim wget curl zip git vsftpd htop
RUN apt-get install -y apache2 
RUN apt-get -y install php7.0 libapache2-mod-php7.0
RUN apt-get -y install snmp php7.0-mysql php7.0-curl php7.0-gd php7.0-intl php-pear php-imagick php7.0-imap php7.0-mcrypt php-memcache  php7.0-pspell php7.0-recode php7.0-sqlite3 php7.0-tidy php7.0-xmlrpc php7.0-xsl php7.0-mbstring php-gettext php-apcu php7.0-zip
RUN apt-get -y install composer
# RUN composer config -g repo.packagist composer http://packagist.phpcomposer.com

ADD 000-default.conf /etc/apache2/sites-enabled/000-default.conf

RUN a2enmod rewrite

EXPOSE 80

CMD /usr/sbin/apache2ctl -D FOREGROUND
 
