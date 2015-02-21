#PHP配置指令

php安装源码路径: `/usr/src/php`  
php安装路径: `/usr/local/etc/php`  

``` bash
./configure \
    --prefix="${PHP_INI_DIR}" \
    --with-config-file-path="${PHP_INI_DIR}" \
    --enable-sockets \
    --enable-ftp \
    --enable-soap \
    --enable-zip \
    --enable-pdo \
    --enable-phar \
    --enable-mbstring \
    --enable-gd-native-ttf \
    --enable-intl \
    --enable-bcmath \
    --enable-xmlwriter \
    --enable-xmlreader \
    --enable-simplexml \
    --enable-libxml \
    --enable-mysqlnd \
    --enable-maintainer-zts \
    --disable-cgi \
    --with-curl \
    --with-iconv \
    --with-gd \
    --with-jpeg-dir \
    --with-png-dir \
    --with-bz2 \
    --with-mcrypt \
    --with-openssl \
    --with-kerberos \
    --with-imap \
    --with-imap-ssl \
    --with-zlib \
    --with-libXML-dir \
    --with-apxs2 \
    --with-readline \
    --enable-maintainer-zts \
```

# 构建
`sudo docker build -t my-php-app .`

# 启动Docker
`sudo docker run -d --name 8080 -v /opt/www:/var/www/html -p 8080:80 build-apache-php`

# 设置 apache 相关的一些变量，在容器启动的时候可以使用 -e 参数替代
ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2
ENV APACHE_PID_FILE /var/run/apache2.pid
ENV APACHE_RUN_DIR /var/run/apache2
ENV APACHE_LOCK_DIR /var/lock/apache2
ENV APACHE_SERVERADMIN admin@localhost
ENV APACHE_SERVERNAME localhost
ENV APACHE_SERVERALIAS docker.localhost
ENV APACHE_DOCUMENTROOT /var/www

[](https://github.com/Vacuum-Z/php/tree/master/5.4/apache)
[](https://github.com/eugeneware/docker-apache-php/blob/master/Dockerfile)

