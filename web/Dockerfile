FROM php:8.1-apache

#Установка php расширений - https://hub.docker.com/_/php How to install more PHP extensions
RUN docker-php-ext-install \
    pdo_mysql \
    && a2enmod \
    rewrite

ENV APACHE_DOCUMENT_ROOT=/var/www/html/public
RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf
RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf

