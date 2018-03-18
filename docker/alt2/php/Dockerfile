FROM php:fpm

LABEL maintainer="Mario Galan <mario.galan@gmail.com>"

EXPOSE 9000

#ADD ../../.. /usr/src/appcoin
#ENV TZ 'Europe/Madrid'
#RUN echo $TZ > /etc/timezone && \
#    apt-get update && apt-get install -y tzdata && \
#    rm /etc/localtime && \
#    ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && \
#    dpkg-reconfigure -f noninteractive tzdata && \
#    apt-get clean
#
#
#RUN apt-get install -y git curl php-cli php-dom php-zip

# Git is needed for composer to run. Libraries installed are needed for the PHP extensions.
RUN apt-get update && apt-get install -y git zlib1g zlib1g-dev libxml2 libxml2-dev

# Install PHP extensions

RUN docker-php-ext-install dom zip pdo_mysql

# Install composer
#RUN curl --silent --show-error https://getcomposer.org/installer | php -- --install-dir=bin --filename=composer

#RUN cd /usr/src/appcoin && /bin/composer install

WORKDIR /var/www
#CMD ["bin/console", "server:run", "0.0.0.0:8000"]