FROM php:8.2-fpm-alpine

# Copy php configuration
ADD ./config/www.conf /usr/local/etc/php-fpm.d/www.conf

# Create user and group
RUN addgroup -g 1000 wp && adduser -G wp -g wp -s /bin/sh -D wp

# Create directory for WordPress
RUN mkdir -p /var/www/html

# Set permissions   
RUN chown wp:wp /var/www/html

# Set working directory
WORKDIR /var/www/html

# Install PHP extensions
RUN docker-php-ext-install mysqli pdo pdo_mysql && docker-php-ext-enable pdo_mysql

# Install WP-CLI
RUN curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN chmod +x wp-cli.phar && mv wp-cli.phar /usr/local/bin/wp