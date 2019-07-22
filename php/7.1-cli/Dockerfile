FROM php:7.1-cli

RUN apt-get update && apt-get install -y zlib1g-dev libicu-dev unzip apt-transport-https gnupg wget git
RUN docker-php-ext-install intl zip pdo pdo_mysql
RUN wget https://nodejs.org/download/release/v8.16.0/node-v8.16.0-linux-x64.tar.gz
RUN mkdir -p /opt/nodejs && tar -xvzf node-v8.16.0-linux-x64.tar.gz -C /opt/nodejs
RUN mv /opt/nodejs/node-v8.16.0-linux-x64 /opt/nodejs/8.16.0 && ln -s /opt/nodejs/8.16.0 /opt/nodejs/current
RUN ln -s /opt/nodejs/current/bin/node /bin/node
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list
RUN apt-get update && apt-get install -y yarn --no-install-recommends
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN echo 'memory_limit = 4G' >> /usr/local/etc/php/conf.d/docker-php-memlimit.ini
RUN composer global require hirak/prestissimo
RUN wget https://get.symfony.com/cli/installer -O - | bash
RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony
