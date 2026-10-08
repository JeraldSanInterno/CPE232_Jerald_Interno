FROM ubuntu:latest

#to avoid the interactive prompts during apt installation
ENV DEBIAN_FRONTEND=noninteractive

#installation of Apache2 web server and MariaDB database server
RUN apt-get update && apt-get install -y \
    apache2 \
    mariadb-server \
    && rm -rf /var/lib/apt/lists/*

#expose HTTP (80) and MySQL/MariaDB (3306) ports
EXPOSE 80 3306

#start the  MariaDB service and run Apache in the foreground
CMD service mariadb start && apachectl -D FOREGROUND
