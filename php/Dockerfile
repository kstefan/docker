FROM php:apache

COPY etc/php /usr/local/etc/php/conf.d

RUN apt-get update && \
    apt-get install -y \
        git zlib1g-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN /usr/local/bin/docker-php-ext-install zip

RUN mkdir /tmp/.composer
ENV COMPOSER_HOME /tmp/.composer
RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer && chmod +x /usr/local/bin/composer
