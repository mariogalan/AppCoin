FROM ubuntu:18.04

# Build with docker build -f ./docker/alt1/Dockerfile -t mariogalan/alt1 .

LABEL maintainer="Mario Galan <mario.galan@gmail.com>"

EXPOSE 8000

COPY . /var/www

# Hack to build the image
ENV TZ 'Europe/Madrid'
RUN echo $TZ > /etc/timezone && \
    apt-get update && apt-get install -y tzdata && \
    rm /etc/localtime && \
    ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata && \
    apt-get clean


RUN apt-get install -y git curl php-cli php-dom php-zip php-mysql mysql-server vim

# Install composer
RUN curl --silent --show-error https://getcomposer.org/installer | php -- --install-dir=bin --filename=composer

# Execute composer
# RUN cd /var/www && /bin/composer install

WORKDIR /var/www

# Define env vars
ENV MYSQL_ROOT_PASSWORD 'root'
ENV MYSQL_DATABASE 'appcoin'
ENV DATABASE_URL 'mysql://root:root@localhost:3306/appcoin'


CMD ["bin/console", "server:run", "0.0.0.0:8000"]

