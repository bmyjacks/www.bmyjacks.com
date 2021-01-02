---
title: How to compile and install the latest version of openssl
tags:
  - openssl
  - ssl
categories:
  - openssl
keywords:
  - openssl
  - ssl
  - web
  - nginx
  - apcache
  - lighttpd
  - canddy
  - https
description: Many friends encountered difficulties when installing openssl, come and see how to completely install the latest version of openssl!
date: 2020-02-15 16:23:39
---

{% note info %}
## info
The system demonstrated in this article is **CentOS7 amd64**, and make sure that openssl is not installed in the system.
{% endnote %}

## First, we first log in to the server background command line page
Enter the command to get the installation package of the latest version (1.1.1d)

```bash
wget https://www.openssl.org/source/openssl-1.1.1d.tar.gz
-Omit the process
xxxx-xx-xx xx:xx:xx (xxx MB/s) - ‘openssl-1.1.1d.tar.gz’ saved [8845861/8845861]
```

### After obtaining the installation package, unzip and enter the directory

```bash
tar -xzf openssl-1.1.1d.tar.gz
cd openssl-1.1.1d
```

### Next configure and compile openssl

{% note warning %}
#### Warning
Please replace `/usr/local/openssl` in the first line of the directory with the location of the directory where you want to install openssl, here we keep the default.
{% endnote %}

```bash
./config --prefix=/usr/local/openssl
./config -t
make
```

{% note info %}
### info
If `/bin/sh: gcc: command not found` appears, then install `gcc` and you can `yum install gcc`
{% endnote %}

### Then install

```bash
make install
```

## Next, let's configure the openssl environment variable

If you enter `openssl version` in the terminal now

The output is similar to the following:

```bash
openssl version
-bash: /usr/bin/openssl: No such file or directory
```

So next we will configure it

### Enter `/usr/local` and create a link

```bash
cd /usr/local
ln -s openssl ssl
```

### Edit the `/etc/ld.so.conf` file

```bash
nano /etc/ld.so.conf
# Add /usr/local/openssl/lib at the end
# Looks like below

include ld.so.conf.d/*.conf
/usr/local/openssl/lib
```

{% note info %}
#### info
If `-bash: nano: command not found` appears, then install `nano` and then `yum install nano`
{% endnote %}

Then, press <kbd>Ctrl</kbd>+<kbd>O</kbd> to save, press <kbd>Ctrl</kbd>+<kbd>X</kbd> to leave nano

Enter `ldconfig` shared dynamic link library

### Configure environment variables Configure environment variables
Edit `.bashrc` file：

```bash
cd 
nano .bashrc
```

Add at the end

```bash
export OPENSSL=/usr/local/openssl/bin
export PATH=$OPENSSL:$PATH:$HOME/bin
```

Save and exit, and use `source .bashrc` to make the changes effective.

## At last
Enter `which openssl` to view the openssl path, and enter `openssl version` to view the version.

```bash
which openssl
# /usr/local/openssl/bin/openssl
openssl version
# OpenSSL 1.1.1d  10 Sep 2019
```
