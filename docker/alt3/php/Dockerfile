FROM php:fpm

LABEL maintainer="Mario Galan <mario.galan@gmail.com>"

EXPOSE 9000

# Libraries installed are needed for the PHP extensions.
RUN apt-get update && apt-get install -y zlib1g zlib1g-dev libxml2 libxml2-dev

# Install PHP extensions
RUN docker-php-ext-install dom zip pdo_mysql


WORKDIR /var/www