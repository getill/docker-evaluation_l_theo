FROM php:8.2-apache

RUN docker-php-ext-install mysqli pdo pdo_mysql

RUN apt-get update && apt-get install -y \
    libmariadb-dev \
    && docker-php-ext-install pdo_mysql \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY . /var/www/html/
