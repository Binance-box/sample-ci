FROM php:7-buster

RUN apt update && apt install -y git
COPY --from=composer:1.10 /usr/bin/composer /usr/bin/composer

ARG sample

RUN mkdir -p /work/server/php-slim
WORKDIR /work/server/php-slim

COPY ${sample}/server/php-slim/composer.* /work/server/php-slim/
RUN composer install -q

COPY ${sample}/client /work/client
COPY ${sample}/server/php-slim /work/server/php-slim
