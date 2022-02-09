FROM php:8.0-fpm
#FROM symfonycorp/cli:latest
#RUN apt-get install -y symfony

RUN apt-get update
RUN apt-get install -y
RUN apt-get autoremove -y
RUN docker-php-ext-install mysqli pdo pdo_mysql
#RUN apt-get install curl -y
#RUN apt-get install git -y
#RUN apt-get install zip -y
#RUN apt-get install nano -y
RUN mkdir /usr/local/bin/symfony
WORKDIR /usr/local/bin/symfony
RUN curl -o installer.sh https://get.symfony.com/cli/installer
RUN chmod +x /usr/local/bin/symfony/installer.sh && /usr/local/bin/symfony/installer.sh

WORKDIR /demo/
COPY . /demo/

RUN symfony new --demo my_project

EXPOSE 8000