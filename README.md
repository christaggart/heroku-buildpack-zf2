Apache+PHP language pack
========================

This is a language pack bundling PHP and Apache for Heroku apps.

Configuration
-------------

The config files are bundled with the LP itself:

* conf/httpd.conf
* conf/php.ini


Pre-compiling binaries
----------------------

    mkdir /app
    wget http://apache.cyberuse.com//httpd/httpd-2.2.19.tar.gz
    tar xvzf httpd-2.2.19.tar.gz
    cd httpd-2.2.19
    ./configure --prefix=/app/apache --enable-rewrite
    make
    make install
    tar -zcvf /app/apache.tar.gz /app/apache

    wget http://us2.php.net/get/php-5.3.6.tar.gz/from/us.php.net/mirror 
    mv mirror php.tar.gz
    tar xzvf php.tar.gz
    cd php-5.3.6/
    ./configure --prefix=/app/php --with-apxs2=/app/apache/bin/apxs --with-mysql --with-pdo-mysql --with-pgsql --with-pdo-pgsql --with-iconv --with-gd --with-config-file-path=/app/php
    make
    make install

    cd /app
    echo '2.2.19' > apache/VERSION
    tar -zcvf apache.tar.gz apache
    echo '5.3.6' > php/VERSION
    tar -zcvf php.tar.gz php