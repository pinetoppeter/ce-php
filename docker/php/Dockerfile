FROM php:7.3.2-apache

RUN mkdir /srv/code

COPY php/000-default.conf /etc/apache2/sites-available/000-default.conf

RUN chown -R www-data:www-data /srv/code
RUN a2enmod rewrite
RUN docker-php-ext-install pdo pdo_mysql
RUN apt-get update && apt-get install -y \
    zlib1g-dev \
    libzip-dev
RUN docker-php-ext-install zip

RUN apt-get install curl
#node version 10
RUN curl -sl https://deb.nodesource.com/setup_10.x | bash
RUN apt-get install -y nodejs
# RUN node -v
# RUN npm -v
# RUN cd /srv/code

# after all copied to srv/code
# CMD cd /srv/code && npm install