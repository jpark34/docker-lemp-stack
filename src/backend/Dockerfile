FROM php:8.1-fpm-alpine

# Install Extensions that are not in the php image we are using
RUN docker-php-ext-install pdo_mysql bcmath

# Install Composer for Laravel
COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

# Create user based on provided user ID
ARG HOST_UID
RUN adduser --disabled-password --gecos "" --uid $HOST_UID demo

# Switch to that user
USER demo