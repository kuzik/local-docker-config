FROM php:7.3-fpm

# install git
RUN apt-get update && \
        apt-get install -y --no-install-recommends git

#install some base extensions
RUN apt-get install -y \
        g++ \
        git \
        curl \
        imagemagick \
        libcurl3-dev \
        libjpeg-dev \
        libmagickwand-dev \
        mariadb-client \
        openssh-client \
        nano \
        unzip \
        redis-server \
        libzip-dev \
        zlib1g-dev \
        zip \
        libpng-dev \
        exiftool \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libicu-dev \
        libpq-dev \
        libxpm-dev \
        libvpx-dev \
        libxml2-dev

RUN docker-php-ext-install -j$(nproc) \
        pdo \
        pcntl \
        soap \
        zip \
        mysqli \
        curl \
        bcmath \
        exif \
        gd \
        iconv \
        intl \
        mbstring \
        opcache \
        pdo_mysql

# Install Imagick
RUN apt-get update && apt-get install -y \
    libmagickwand-dev --no-install-recommends \
    && pecl install imagick \
	&& docker-php-ext-enable imagick

# Install Composer
RUN echo "Install Composer"
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version