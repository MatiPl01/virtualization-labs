FROM composer:latest as builder

WORKDIR /var/www/html

RUN composer create-project flarum/flarum . --stability=beta

FROM php:8.1-apache

COPY --from=builder /var/www/html /var/www/html

RUN apt-get update && \
    apt-get install -y \
      libpng-dev \
      zlib1g-dev \
      mariadb-client \
      libonig-dev \
    && docker-php-ext-install pdo_mysql mbstring gd \
    && a2enmod rewrite

RUN chown -R www-data:www-data /var/www/html \
    && chmod -R 755 /var/www/html

COPY ./000-default.conf /etc/apache2/sites-available/000-default.conf

EXPOSE 80
CMD ["apache2-foreground"]

# docker build -t flarum-forum .
# docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=password -d mysql:latest
# docker exec -it mysql-container mysql -uroot -p

# CREATE DATABASE flarum;
# CREATE USER 'myuser'@'%' IDENTIFIED BY 'mypassword';
# GRANT ALL PRIVILEGES ON flarum.* TO 'myuser'@'%';
# FLUSH PRIVILEGES;
# exit

# docker run -d --name flarum-forum --link mysql-container:mysql -p 8080:80 flarum-forum
