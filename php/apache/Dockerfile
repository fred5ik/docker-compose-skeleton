FROM php:5.6-apache
MAINTAINER Fred

RUN apt-get update
RUN apt-get install -y vim libcurl4-openssl-dev zip

RUN docker-php-ext-install \
	mysqli \
	pdo_mysql \
	curl \
	&& docker-php-source delete 

RUN php -r "readfile('https://getcomposer.org/installer');" | php -- --install-dir=/usr/local/bin --filename=composer

RUN chmod +x /usr/local/bin/composer
RUN chmod +w /var/www

RUN useradd -ms /bin/bash fred5ik

COPY php.ini /usr/local/etc/php/php.ini

