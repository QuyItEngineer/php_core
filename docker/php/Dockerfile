FROM php:7.1-fpm

RUN apt-get update && apt-get install -y libmcrypt-dev wget gnupg 
RUN apt-get update && apt-get install -y default-mysql-client libmagickwand-dev git zip unzip --no-install-recommends \
    && pecl install imagick xdebug \
    && docker-php-ext-enable imagick \
    && docker-php-ext-install mcrypt pdo_mysql xml gd mbstring opcache pcntl zip \
    && docker-php-ext-enable zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/bin/composer \
    && composer --version