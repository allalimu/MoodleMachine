# Moodle Clean Installation Commands

## Requirements:

Look into the vagrant File.

## Commands:

### Apache Installation

    > sudo apt update

    > sudo apt install apache2

    > sudo ufw app list

    > sudo ufw app info "Apache Full"

    > sudo ufw allow in "Apache Full"

    > sudo apt update

### Mysql Installation

    > sudo apt install mysql-server

    > sudo mysql_secure_installation

Here, a Problem will arise, and this is the diagnosis/solution.

    > sudo mysql -u root

Had to use "sudo" since is new installation

    mysql> USE mysql;
    mysql> SELECT User, Host, plugin FROM mysql.user;

As you can see in the query, the root user is using the auth_socket plugin.

    mysql> USE mysql;
    mysql> UPDATE user SET plugin='mysql_native_password' WHERE User='root';
    mysql> FLUSH PRIVILEGES;
    mysql> exit;

Now, we must restart the serivce for the new configurations to be accepted.

    > sudo service mysql restart

### php installation

The Current Moodle version in production has php7.4, so that's what i'm going to install.

    > sudo apt update

    > sudo apt -y install software-properties-common

    > sudo add-apt-repository ppa:ondrej/php

    > sudo apt update

    > sudo apt -y install php7.4

php 7.4 pcre and spl extensions are installed by default and are enabled.

    > sudo apt install php7.4-json php7.4-iconv php7.4-mbstring curl php7.4-curl php7.4-mysql php7.4-xml unzip php7.4-zip openssl php7.4-xmlrpc php7.4-dom php7.4-intl php7.4-simplexml php7.4-gd php7.4-ctype php7.4-soap php7.4-tokenizer 
