FROM alari/php-fpm-53

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install git php5-memcached php5-memcache php5-intl php5-mysql php5-gd phpunit memcached php5-xdebug php5-curl libxrender1 \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

#composer
RUN set -x \
    && cd /tmp \
    && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
#    && php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
    && php composer-setup.php --install-dir=/usr/bin --filename composer \
    && php -r "unlink('composer-setup.php');"

WORKDIR "/var/www/html/bhotel"
