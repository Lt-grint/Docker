FROM php:7.1-fpm

# 配置依赖
RUN set -ex \
&& cd ~ \
&& mv /etc/apt/sources.list /etc/apt/sources.list.bak \
&& { \
echo deb http://mirrors.aliyun.com/debian/ jessie main non-free contrib; \
echo deb http://mirrors.aliyun.com/debian/ jessie-proposed-updates main non-free contrib; \
echo deb-src http://mirrors.aliyun.com/debian/ jessie main non-free contrib; \
echo deb-src http://mirrors.aliyun.com/debian/ jessie-proposed-updates main non-free contrib; \
} | tee /etc/apt/sources.list \
&& apt-get update \
&& apt-get install -y git \
apache2 \
libpcre3-dev \
libfreetype6-dev \
libjpeg62-turbo-dev \
libmcrypt-dev \
libpng12-dev 

# 安装php扩展
RUN  docker-php-ext-install -j$(nproc) iconv mcrypt \
&& docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
&& docker-php-ext-install -j$(nproc) gd \
&& docker-php-ext-install pdo_mysql  \
&& docker-php-ext-install zip

EXPOSE 9000
CMD ["php-fpm"]

