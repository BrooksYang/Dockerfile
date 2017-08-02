# PHP7 Running
# For laravel with FTP Mongodb support 
FROM ubuntu:16.04
MAINTAINER Brooks Yang <brooksyang@outlook.com>

ENV DEBIAN_FRONTEND noninteractive

# ADD sources.list.trusty /etc/apt/sources.list
RUN apt-get update

# RUN apt-get install -y libreoffice
RUN apt-get install -y vim wget curl zip git vsftpd htop
RUN apt-get install -y apache2 
RUN apt-get -y install php7.0 libapache2-mod-php7.0
RUN apt-get -y install snmp php7.0-mysql php7.0-curl php7.0-gd php7.0-intl php-pear php-imagick php7.0-imap php7.0-mcrypt php-memcache  php7.0-pspell php7.0-recode php7.0-sqlite3 php7.0-tidy php7.0-xmlrpc php7.0-xsl php7.0-mbstring php-gettext php-apcu php7.0-zip
RUN apt-get -y install composer

RUN apt-get -y install php7.0-dev php-mongodb
RUN apt-get -y install libcurl4-openssl-dev pkg-config libssl-dev libsslcommon2-dev

RUN pecl install mongodb

ADD 000-default.conf /etc/apache2/sites-enabled/000-default.conf
ADD php.ini /etc/php/7.0/apache2/php.ini
ADD php.ini /etc/php/7.0/cli/php.ini

RUN a2enmod rewrite

ADD vsftpd.conf /etc/vsftpd.conf
RUN useradd -m yunchang -s /usr/sbin/nologin
RUN echo 'yunchang:123456' | chpasswd
RUN echo "/usr/sbin/nologin" >> /etc/shells
RUN mkdir /opt/yunchang
RUN usermod -d /opt/yunchang yunchang
RUN chown yunchang:yunchang /opt/yunchang


EXPOSE 80
EXPOSE 21
EXPOSE 40000

CMD /usr/sbin/apache2ctl -D FOREGROUND
 
