FROM php:7.4.25-fpm-bullseye
RUN apt-get update && \
    apt-get install -y libldap2-dev \
    libzip-dev  \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    zip \
    unzip
RUN docker-php-ext-configure gd --with-freetype --with-jpeg
RUN docker-php-ext-install -j$(nproc) ldap \
    zip \
    bcmath \
    gd \
    pdo_mysql
WORKDIR /usr/share/nginx/html/