FROM alpine:3.8
LABEL maintainer="Name <foo@bar.com>"
RUN addgroup -g 5000 fpm && \
    adduser -SH \
    -s /sbin/nologin \
    -u 5000 \
    -h /var/www/html \
    -G fpm fpm   
RUN apk update && apk upgrade
RUN apk add php7 \
php7-fpm \
php7-pdo \
php7-pdo_mysql \
php7-mcrypt \
php7-mbstring \
php7-xml \
php7-openssl \
php7-json \
php7-phar \
php7-zip \
php7-dom \
php7-session \
php7-zlib \
bash
COPY php.ini /etc/php7/php-fpm.d/www.conf
EXPOSE 9000
CMD /usr/sbin/php-fpm7 --nodaemonize --fpm-config /etc/php7/php-fpm.d/www.conf
