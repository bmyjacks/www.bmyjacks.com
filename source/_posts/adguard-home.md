---
title: Use AdGuard Home to filter ads
tags:
  - Ad Guard
  - Pi-hole
categories:
  - Ad Guard
keywords:
  - AdGuard Home
  - Pihole
  - ads
  - dns
description: Nowadays, the numerous and complicated advertisements on the Internet seriously disturb our pleasure when surfing the Internet. Why not install AdGuard Home to filter the advertisements at home?
date: 2020-03-09 20:46:28
---

{% note info %}
### info
Since `AdGuard Home` only supports the `Debian` at present, we use  **debian9 AMD64** to demonstrate it.
{% endnote %}

## First, download the installation package to the server
### Open the official GitHub page
[https://github.com/AdguardTeam/AdGuardHome](https://github.com/AdguardTeam/AdGuardHome)

Click`releases`

![GitHub-Releases-Page](https://assets.bmyjacks.cn/img/20200309194654.png?x-oss-process=style/style)

Download the latest version

![Downloading](https://assets.bmyjacks.cn/img/20200309194854.png?x-oss-process=style/style)

### After downloading, unzip it and into the folder
```bash
tar -xzvf AdGuardHome_linux_amd64.tar.gz
cd AdGuardHome/
```

![Folder](https://assets.bmyjacks.cn/img/20200309201502.png?x-oss-process=style/style)

Install the dependency `sudo apt-get install sudo nano bind9-host`

Input `sudo ./AdGuardHome -s install` to install AdGuard Home

## Open web panel
Visit`http://ip:3000`，Click Next until this page

![confirgure](https://assets.bmyjacks.cn/img/20200309202015.png?x-oss-process=style/style)

Fill in your password and click next to complete the installation.

## Set your DNS server to AdGuard Home
Set the DNS server to your `AdGuard Home` IP address on the router, or turn off DHCP on the router and use the DHCP provided by `AdGuard Home`.

{% note success %}
## Congratulations
Congratulations to you，Installation of `AdGuard Home` completed successfully!
{% endnote %}

## Common commands
| Purpose                  | Commands                 |
| ------------------------ | ------------------------ |
| Start the service        | AdGuardHome -s start     |
| Stop the service         | AdGuardHome -s stop      |
| Restart the service      | AdGuardHome -s restart   |
| Check the service status | AdGuardHome -s status    |
| Uninstall the service    | AdGuardHome -s uninstall |
