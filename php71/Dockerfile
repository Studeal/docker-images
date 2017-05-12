FROM php:7.1

RUN apt-get update && apt-get install -y unzip zip libfreetype6-dev libjpeg62-turbo-dev libpng12-dev wkhtmltopdf && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ && docker-php-ext-install -j$(nproc) gd && docker-php-ext-install zip

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN composer global require hirak/prestissimo
