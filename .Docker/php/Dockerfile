FROM php:7.2-fpm

# Install recommended extensions for Symfony
RUN apt-get update && apt-get install -y \
        libicu-dev \
    && docker-php-ext-install \
        intl \
        opcache \
    && docker-php-ext-enable \
        intl \
        opcache \
    && docker-php-ext-install pdo pdo_mysql \
    && docker-php-ext-install mysqli

RUN apt-get install -y \
    zip \
    unzip \
    zlib1g-dev \
    libpng-dev \
    libc-client-dev \
    libtidy-dev \
    libkrb5-dev \
    && rm -r /var/lib/apt/lists/*
    
RUN docker-php-ext-configure imap --with-kerberos --with-imap-ssl \
    && docker-php-ext-install -j$(nproc) imap \
    && docker-php-ext-install gd \
    && docker-php-ext-install tidy \
    && docker-php-ext-enable tidy

RUN chown -R www-data:www-data /var/www
RUN chmod 755 /var/www