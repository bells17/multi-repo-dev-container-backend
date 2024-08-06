FROM php:8.3.10-fpm-bullseye as dev-env
WORKDIR /workspace

COPY --from=composer:2.7.7 /usr/bin/composer /usr/bin/composer
RUN apt-get update && apt-get install -y \
    git \
    unzip \
    libzip-dev \
    && docker-php-ext-install zip pdo_mysql

CMD ["php", "-S", "0.0.0.0:8000", "-t", "public"]
