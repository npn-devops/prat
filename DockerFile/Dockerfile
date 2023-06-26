# Base image
FROM php:8.1-fpm

# Install additional dependencies
RUN apt-get update && apt-get install -y \
    libzip-dev \
    zip \
    unzip \
    && docker-php-ext-install \
    zip \
    pdo_mysql

# Copy php-fpm configuration file
COPY php-fpm.conf /usr/local/etc/php-fpm.d/www.conf

# Set the working directory
WORKDIR /var/www/html

# Expose port 9000 for PHP-FPM
EXPOSE 9000

# Start PHP-FPM
CMD ["php-fpm"]

