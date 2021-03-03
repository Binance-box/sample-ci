FROM php:7-buster

RUN apt update && apt install -y git
COPY --from=composer:1.10 /usr/bin/composer /usr/bin/composer

ARG sample

RUN mkdir -p /work/server/php
WORKDIR /work/server/php

COPY ${sample}/server/php/composer.* /work/server/php/
RUN composer install -q

COPY ${sample}/client /work/client
COPY ${sample}/server/php /work/server/php
