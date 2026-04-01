FROM php:8.2-cli

WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git unzip zip

# Install Composer inside container
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Install PHP extensions (optional)
RUN docker-php-ext-install sockets

CMD ["tail", "-f", "/dev/null"]