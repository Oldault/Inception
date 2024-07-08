FROM alpine:3.19

RUN apk update && apk add --no-cache \
    php81 \
    php81-fpm \
    php81-mysqli \
    curl

RUN mkdir -p /var/www/html

RUN curl -o /wordpress.tar.gz https://wordpress.org/latest.tar.gz && \
    tar -xzf /wordpress.tar.gz -C /var/www/html && \
    rm /wordpress.tar.gz

COPY ./config/wp-config.php /var/www/html/wordpress/wp-config.php

EXPOSE 9000

CMD ["php-fpm81", "--nodaemonize"]
