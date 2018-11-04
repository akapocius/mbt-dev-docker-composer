FROM phpdockerio/php56-fpm:latest

# Install selected extensions and other stuff
RUN apt-get update \
    && apt-get -y --no-install-recommends install locales locales-all php5-mysql php5-gd php5-intl git php5-memcached php5-memcache \
    && apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

# RUN locale-gen en_US.UTF-8 && locale-gen fr_FR.UTF-8 && locale-gen es_CR.UTF-8 && locale-gen ar_SA.UTF-8

WORKDIR "/var/www/html/application"
