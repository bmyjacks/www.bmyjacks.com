---
title: How to install nginx from source code
tags:
  - nginx
categories:
  - nginx
keywords:
  - nginx
  - web
  - webserver
  - www
  - website
description: As a famous web server, how can nginx experience the thrill of high concurrency without installing it?
date: 2020-02-16 16:52:17
---

{% note info %}
## info
The system demonstrated in this article is **CentOS7 amd64**, and make sure that nginx or other website server is not installed in the system.
{% endnote %}

## First, we need to make preparations before installation
### Install some compilation tools first

Open the terminal and input:

```bash
yum install gcc gcc-c++ autoconf automake make zlib zlib-devel openssl openssl-devel pcre pcre-devel
```

After outputting `Complete!` in the console, proceed to the next step.

### Add WWW user

enter:

```bash
groupadd -f www
useradd -g www www
```

## Start to enter the formal link
### Obtain the installation source code

First enter [nginx official website](http://nginx.org/en/download.html)to check the latest version

![](https://cdn.bmyjacks.io/img/20200309175844.png?x-oss-process=style/style)

Choose the latest `1.17.8` version here

```bash
wget http://nginx.org/download/nginx-1.17.8.tar.gz
```

After obtaining the installation package, unzip it:

```bash
tar -zxvf nginx-1.17.8.tar.gz
```

### Configure nginx

Enter folder

```bash
cd nginx-1.17.8
```

Configure nginx

```bash
#--prefix=The directory where you want to install nginx, for example:
#--prefix=/usr/local/nginx

./configure --user=www --group=www --prefix=/usr/local/nginx --with-http_stub_status_module --with-http_ssl_module --with-stream --with-http_gzip_static_module --with-http_sub_module
```

![](https://cdn.bmyjacks.io/img/20200309175912.png?x-oss-process=style/style)

Seeing the configuration result shows that the configuration is successful

### Install nginx

First compile nginx

```bash
make
```

Then install

```bash
make install

```

Start the service and visit the corresponding IP address

```bash
/usr/local/nginx/sbin/nginx
```

![](https://cdn.bmyjacks.io/img/20200309175943.png?x-oss-process=style/style)

## Other usage matters

| intention             | command                                |
| --------------------- | -------------------------------------- |
| Start nginx service   | /usr/local/nginx/sbin/nginx            |
| Stop nginx service    | /usr/local/nginx/sbin/nginx -s stop    |
| Restart nginx service |  /usr/local/nginx/sbin/nginx -s reload |

Store the webpage in the `/usr/local/nginx/html/` directory.
