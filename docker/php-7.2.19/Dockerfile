FROM php:7.2.19-apache
MAINTAINER Misley Márton <misley.marton@webdream.hu>

# configure and install extra dependencies
RUN apt-get update \
    && apt-get install -y \
        # intl dependency
        libicu-dev \
        # zip extension dependency
        zlib1g-dev \
    && apt-get clean \
    && docker-php-ext-configure intl \
    && docker-php-ext-install \
        intl \
        opcache \
        pdo_mysql \
        zip \
    # install & enable apcu
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    # disable default apache vhost
    && a2dissite 000-default.conf \
    # enable apache rewrite engine
    && a2enmod rewrite
