FROM php:8.1-apache

RUN docker-php-ext-install pdo_mysql
RUN a2enmod rewrite

RUN chown -R www-data:www-data /var/www

WORKDIR /var/www

RUN apt-get update && apt-get install -y curl git zip unzip

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer \
    && ln -s $(composer config --global home) /root/composer

ENV PATH=$PATH:/root/composer/vendor/bin COMPOSER_ALLOW_SUPERUSER=1

RUN composer install

RUN cp .env.example .env

RUN php artisan key:generate

EXPOSE 8000
