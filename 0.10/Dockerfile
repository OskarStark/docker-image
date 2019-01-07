FROM php:7.3-alpine
MAINTAINER Tommy Muehle <tommy.muehle@gmail.com>

ENV COMPOSER_HOME /composer
ENV COMPOSER_ALLOW_SUPERUSER 1
ENV PATH /composer/vendor/bin:$PATH
ENV PHPSTAN_VERSION 0.10.x

COPY --from=composer:1.8.0 /usr/bin/composer /usr/local/bin/composer

RUN composer global require phpstan/phpstan ^0.10 \
    && composer global show | grep phpstan

VOLUME ["/app"]
WORKDIR /app

ENTRYPOINT ["phpstan"]
