FROM php:8.1-apache

RUN docker-php-ext-install pdo_mysql
RUN a2enmod rewrite

RUN chown -R www-data:www-data /var/www

WORKDIR /var/www

RUN apt-get update && apt-get install -y curl git zip unzip

RUN cp .env.example .env

RUN php artisan key:generate

EXPOSE 8000
