FROM php:5.6-apache
RUN mkdir -p /etc/php5/cli; curl -sS "https://raw.githubusercontent.com/php/php-src/master/php.ini-development" > /etc/php5/cli/php.ini
RUN apt-get update -y
RUN apt-get install -y curl zip unzip
RUN curl -sS https://getcomposer.org/installer | php
RUN php composer.phar require neoxygen/neoclient
RUN apt-get install -y wget
RUN wget -O - http://dl.hhvm.com/conf/hhvm.gpg.key | apt-key add -
RUN echo deb http://dl.hhvm.com/debian jessie main | tee /etc/apt/sources.list.d/hhvm.list
RUN apt-get update
RUN apt-get install -y hhvm
RUN apt-get install -y php5-mysql
RUN apt-get install -y libssl-dev
RUN pecl install mongodb
RUN echo "extension=mongodb.so" >> `php --ini | grep "Loaded Configuration" | sed -e "s|.*:\s*||"`
RUN echo "extension=mongodb.so" >> '/etc/php5/cli/php.ini'
RUN ln -s /etc/php5/cli/php.ini /usr/local/etc/php/php.ini
RUN php composer.phar require "mongodb/mongodb=^1.0.0"
RUN apt-get install -y mongodb-clients
