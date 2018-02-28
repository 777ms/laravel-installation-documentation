# Laravel environment configuration(in centos 6.9)

PHP

Error encountered when I configured

```
1、undefined reference to '_iconv' or any inssues with libiconv,tried to reset the package 'libiconv'.
Add '--with-iconv=/usr/local' at compile time. Remember,when you install 'libiconv' and don't forget execute './configure --prefix=/usr/local'

2、
cc: Internal error: Killed (program cc1)
Please submit a full bug report.
See <http://bugzilla.redhat.com/bugzilla> for instructions.
make: *** [libmagic/apprentice.lo] Error 1

add '--disable-fileinfo'

```


## Compile and install php7
```
$ wget http://cn2.php.net/get/php-7.1.0.tar.gz/from/this/mirror
$ tar zvxf mirror
$ cd php-7.1.0

$ ./configure --prefix=/usr/local/php7 \
--with-config-file-path=/usr/local/php7/etc \
--with-config-file-scan-dir=/usr/local/php7/etc/php.d \
--with-mcrypt=/usr/include \
--enable-mysqlnd \
--with-mysqli \
--with-pdo-mysql \
--enable-fpm \
--with-fpm-user=nginx \
--with-fpm-group=nginx \
--with-gd \
--with-iconv=/usr/local \
--with-zlib \
--enable-xml \
--enable-shmop \
--enable-sysvsem \
--enable-inline-optimization \
--enable-mbregex \
--enable-mbstring \
--enable-ftp \
--enable-gd-native-ttf \
--with-openssl \
--enable-pcntl \
--enable-sockets \
--with-xmlrpc \
--enable-zip \
--enable-soap \
--without-pear \
--with-gettext \
--enable-session \
--with-curl \
--with-jpeg-dir \
--with-freetype-dir \
--enable-opcache

$ make && make install
```
