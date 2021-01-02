---
title: Use Pi-hole to filter ads
tags:
  - Pi-hole
  - DNS
  - Ad Guard
categories:
  - Pi-hole
keywords:
  - pihole
  - ads
  - AdGuard
  - dns
description: Nowadays, the numerous and complicated advertisements on the Internet seriously disturb our pleasure when surfing the Internet. Why not install Pi-hole to filter the advertisements at home?
date: 2020-02-29 18:49:47
---

{% note info %}
## info
The system demonstrated in this article is **Debian9 amd64**, other versions can be installed according to actual conditions.
{% endnote %}

## First, we update the system
Terminal input:
```bash
sudo apt update
sudo apt upgrade -y
```

## Next, we start to install Pi-hole

You can enter [Pi-hole's GitHub page](https://github.com/pi-hole/pi-hole) to install, or follow the steps below.

Get the installation script first:
```bash
wget -O basic-install.sh https://install.pi-hole.net
```

Next, we execute the script:
```bash
sudo bash basic-install.sh
```

After seeing Pi-hole’s logo, I entered the installation page, and then hit enter directly to the following page,

Use the arrow keys to scroll to the bottom and select `Custom`:
![](https://cdn.bmyjacks.io/img/20200309180649.png?x-oss-process=style/style)

Enter the upstream DNS address (here, take Alibaba Cloud and Baidu as examples):
![](https://cdn.bmyjacks.io/img/20200309180701.png?x-oss-process=style/style)


After a series of carriage returns came to this page:
![](https://cdn.bmyjacks.io/img/20200309180712.png?x-oss-process=style/style)


```bash
On #Means to the install the web control page
Off #Means not to install the web control page
```

Here we choose `On` and press Enter to the next step
![](https://cdn.bmyjacks.io/img/20200309180726.png?x-oss-process=style/style)

Here you choose whether to install the web server (lighttpd). If you have installed the web server (such as nginx, apache) on the server, select `Off`, otherwise select `On` to install the lighttpd server.

Then directly press Enter several times to start the installation.

## Finally, let’s Configure Pi-hole
### First change the password of the web control page
Terminal input:

```bash
pihole -a -p
```

After the modification is completed, visit the browser `http://localhost/admin` to enter the web control page
![](https://cdn.bmyjacks.io/img/20200309180738.png?x-oss-process=style/style)

Click on `Login` on the left to log in
![](https://cdn.bmyjacks.io/img/20200309180757.png?x-oss-process=style/style)

Enter the password you just set, you can tick remember.
![](https://cdn.bmyjacks.io/img/20200309180757.png?x-oss-process=style/style)

Click on `Settings` on the left to enter the settings page
![](https://cdn.bmyjacks.io/img/20200309180818.png?x-oss-process=style/style)

Here we can see various settings:
```bash
System #Monitoring the operating status of the system
Blocklists #Ad block list
DNS #Upstream DNS server configuration
DHCP #Use Pihole as your DHCP server
API/Web interface #关于API和web控制页面的设定
Privacy #Privacy settings
Teleporter #Report error
```

You can adjust the settings according to your needs.

### Several commonly used settings are recommended:

You can add my blocklist to the blocklist: [https://cdn.jsdelivr.net/gh/bmyjacks/adhosts@latest/big_edition.txt)

Adjust DNS cache size:
Terminal modification file:
```bash
sudo nano /etc/dnsmasq.d/01-pihole.conf
# find cache-size=10000
# Modify 10000 to the value you want, for example
cache-size=200000
# Save, exit
```
Then restart the DNS server on the web control page
![](https://cdn.bmyjacks.io/img/20200309180857.png?x-oss-process=style/style)


## Set Pi-hole as your DNS server
Set the DNS server to your Pi-hole on the router, or turn off the router's DHCP and use the DHCP provided by Pi-hole.

{% note success %}
## Congratulations
Congratulations, you have successfully completed the installation of Pi-hole, and start enjoying almost ad-free web surfing.
{% endnote %}
