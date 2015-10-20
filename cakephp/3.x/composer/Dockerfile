FROM cake17/php-fpm

MAINTAINER cake17 <cake17@cake-websites.com>

# Set memory limit
RUN echo "memory_limit=1024M" > /usr/local/etc/php/conf.d/memory-limit.ini

# Set environmental variables
ENV COMPOSER_HOME /root/composer

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer --version=1.0.0-alpha8

# Display version information
RUN php --version
RUN composer --version

# Set up the command arguments
CMD ["-"]
ENTRYPOINT ["composer", "--ansi"]
