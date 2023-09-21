FROM php:8.2-fpm

ARG user
ARG uid

EXPOSE 9000

RUN apt-get update

RUN apt-get install -y libzip-dev \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip

RUN apt-get clean && rm -rf /var/lib/apt/lists/*

RUN docker-php-ext-install zip pdo_mysql mbstring exif pcntl bcmath gd

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN useradd -G www-data,root -u $uid -d /home/$user $user
RUN mkdir -p /home/$user/.composer && \
    chown -R $user:$user /home/$user

WORKDIR /app

USER $user

#CMD ["php-fpm"]
