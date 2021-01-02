---
title: Teach you how to install manjaro
tags:
  - manjaro
  - linux
categories:
  - manjaro
keywords:
  - manjaro
  - linux
  - arch
  - arch linux
date: 2020-03-31 18:02:09
description: After using windows for a long time, do you want to switch to linux? Let's take a look at how to install manjaro!
---

## Download images and tools
### Download the manjaro image
Go to [manjaro official website](https://manjaro.org/download/)

![manjaro-install](https://cdn.bmyjacks.io/img/20200331085728.png?x-oss-process=style/style)

```bash
XFCE #A lightweight desktop system
KDE Plasma #The most commonly used KDE desktop system
GNOME #The same desktop system as Ubuntu
Architect #There is no desktop version, only the terminal, you need to use the terminal to install
```

We choose `KDE Plasma` to download

### Download tool
Go to [rufus official website](http://rufus.ie/)and download [rufus](https://github.com/pbatard/rufus/releases/download/v3.9/rufus-3.9.exe)

![rufus website](https://cdn.bmyjacks.io/img/20200331091353.png?x-oss-process=style/style)

## Write image
Open rufus
![rufus tool](https://cdn.bmyjacks.io/img/20200331155031.png?x-oss-process=style/style)
Select the inserted disk in the device, select the downloaded image, click start, and wait for a while

## install the manjaro
## Boot from USB
Restart the computer, enter the BIOS when the logo is displayed (You can try to press ESC)
Then choose to boot from the disk, turn off the system `Secure boot` and `Launch CSM`

{% note info %}
### info
Use UEFI to boot on modern computers.
{% endnote %}

## Start installing
After booting from the U disk, the following screen appears

![boot](https://cdn.bmyjacks.io/img/20200331155930.png?x-oss-process=style/style)

Use your custom configuration instead of the configuration in the picture

![boot](https://cdn.bmyjacks.io/img/20200331160034.png?x-oss-process=style/style)

Select `boot` and click <kbd>Enter</kbd> to enter the live system

![manjaro live](https://cdn.bmyjacks.io/img/20200331160423.png?x-oss-process=style/style)

Close the welcome screen, double click the first item on the desktop `Install Manjaro Linux` to enter the installer

![install manjaro](https://cdn.bmyjacks.io/img/20200331160830.png?x-oss-process=style/style)

Use your custom configuration instead of the configuration in the picture

![choose language](https://cdn.bmyjacks.io/img/20200331161011.png?x-oss-process=style/style)

![time zones](https://cdn.bmyjacks.io/img/20200331161145.png?x-oss-process=style/style)

![keyboard](https://cdn.bmyjacks.io/img/20200331161323.png?x-oss-process=style/style)
At this step, you can choose either `Erase Disk` or `Manual Partition`. If you choose `Erase Disk`, you can directly watch the subsequent installation. If you choose `Manual Partition`, please continue to look down.

![disk](https://cdn.bmyjacks.io/img/20200331162312.png?x-oss-process=style/style)

Click New Partition Table, select `GUID Partition Table (GPT)` format, click Next

{% note info %}
### info
Recommend UEFI+GPT.
{% endnote %}

Partition according to your needs

File system

```bash
etx2
etx3
etx4 #Default file system
linuxswap #swap file system
fat16
fat32 #File system used by boot
ntfs #File system frequently used on Windows
reiser
xfs #Commonly used
jfs
Unformatted
brtfs #Commonly used
luks
exfat #Cross-platform file system
nilfs2
lvm2 pv
f2fs #Commonly used
luks2
fat12
minix
```

Mount point

```bash
(no mount point) #Don't mount
/ #Main directory
/boot #boot directory
/boot/efi #Directory for EFI boot
/home #Directory to store user files
/opt #Directory for storing additional installers
/srv #A directory that stores services or data provided by the machine or server to the outside world
/usr #Store system applications
/var #Store files that need to be changed during runtime, such as log
```

Swap partition size scheme

| RAM size | No sleep function | Has sleep function | Max    |
| -------- | ----------------- | ------------------ | ------ |
| 256MB    | 256MB             | 512MB              | 512MB  |
| 512MB    | 512MB             | 1024MB             | 1024MB |
| 1024MB   | 1024MB            | 2048MB             | 2048MB |
| 2GB      | 1GB               | 3GB                | 2GB    |
| 4GB      | 2GB               | 5GB                | 8GB    |
| 8GB      | 3GB               | 11GB               | 16GB   |
| 16GB     | 4GB               | 20GB               | 32GB   |
| 32GB     | 6GB               | 38GB               | 64GB   |
| 64GB     | 8GB               | 72GB               | 128GB  |
| 128GB    | 11GB              | 139GB              | 256GB  |

{% note info %}
### info
It is not recommended to enable hibernation for 64G RAM and above.
{% endnote %}

Partition scheme

```bash
/boot/efi #512MiB FAT32
/ #The remaining partition ETX4
/swap #Select the memory size when the memory size is 2G-8G, and 4G when it is greater than 8G
```

The scheme used by the blogger, three hard drives, SSD1 240G SSD2 500G HDD 2T.

```bash
/boot/efi # 512MiB FAT32 SSD1
/home # The remaining size of SSD1 XFS SSD1
/opt # 200G XFS SSD2
/srv # 500G XFS HDD
/usr # 250G XFS SSD2
/var # 50G XFS SSD2
/swap # 20G linuxswap HDD
```

After adjusting the partition, we started the installation
![install manjaro](https://cdn.bmyjacks.io/img/20200331175142.png?x-oss-process=style/style)

Fill in the name and password, the next step

![username password](https://cdn.bmyjacks.io/img/20200331175554.png?x-oss-process=style/style)

Select the office suite to install
```bash
No Office Suite #Do not install Office Suite
LibreOffice #Office software under Linux that bloggers prefer
FreeOffice #The blogger has never used it, and doesn’t know whether it’s good or bad
```

Continue to click Next, check that the changes are the same as you thought, click Install

## Start the installed system
After the installation is complete, turn off the computer, pull out the U disk, and turn on the desktop. Wow!

![manjaro desktop](https://cdn.bmyjacks.io/img/20200331182148.png?x-oss-process=style/style)

Turn off `Launch at start` so that the system is installed.
