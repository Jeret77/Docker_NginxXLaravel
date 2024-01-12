FROM php:8.0-fpm



RUN apt-get update && apt-get install -y \
    libpng-dev \
    libjpeg-dev \
    libfreetype6-dev \ 
    libzip-dev \ 
    zip \
    unzip \
    git \
    curl

RUN docker-php-ext-configure gd --with-freetype --with-jpeg \
&& docker-php-ext-install -j$(nproc) gd pdo pdo_mysql zip

#Installer composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

#Installer Node.js
RUN curl -sL https://deb.nodesource.com/setup_14.x | bash - && apt-get install -y nodejs

WORKDIR /var/www


    
