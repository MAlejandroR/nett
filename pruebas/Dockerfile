FROM ubuntu:latest
ARG DEBIAN_FRONTEND=noninteractive
RUN apt update && apt -y install \
    apache2\
    php\
    libapache2-mod-php
COPY index.php /var/www/html/index.php    