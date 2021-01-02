---
title: Qt tutorial (1)-install Qt
tags:
  - qt
  - gui
categories:
  - qt
keywords:
  - qt
  - GUI
  - QT
description: Use Qt to write a graphical interface for desktop window applications? This tutorial teaches you how to install Qt
date: 2020-02-19 22:07:08
---

{% note info %}
## info
The system demonstrated in this article is **Windows10Pro 64bit**
{% endnote %}

## First, we enter [download Qt page](http://download.qt.io/)

![](https://assets.bmyjacks.cn/img/20200309180333.png?x-oss-process=style/style)


The file structure is similar to:

```bash
- snapshots/ #Latest snapshot version
- online/ #Online installer
- official_releases/ #Official release version
- new_archive/ #New archive version
- ministro/ #Mini version, currently for Android
- linguist_releases/
- learning/ #Learning materials
- development_releases/ #Development version
- community_releases/ #Community version, such as Tizen
- archive/ #Archive version
- timestamp.txt #Timestamp
```

The demo uses offline installation

Click to enter [official_releases/qt/5.14/5.14.1/](http://download.qt.io/official_releases/qt/5.14/5.14.1/)

![](https://assets.bmyjacks.cn/img/20200309180345.png?x-oss-process=style/style)


There are three installation files:

```bash
- qt-opensource-windows-x86-5.14.1.exe #Windows installation files
- qt-opensource-mac-x64-5.14.1.dmg #MacOS installation files
- qt-opensource-linux-x64-5.14.1.run #Linux installation files
```

Since we are using Windows, select the first installation file and click on `Details` behind the installation file to view details

![](https://assets.bmyjacks.cn/img/20200309180345.png?x-oss-process=style/style)

Get the installation file after downloading

![](https://assets.bmyjacks.cn/img/20200309180410.png?x-oss-process=style/style)


## Now let's start the installation

Double-click to open the installer, you need to log in after clicking `Next`

![](https://assets.bmyjacks.cn/img/20200309180420.png?x-oss-process=style/style)


{% note warning %}
### Notice
To register an account, go to [**website**](www.qt.io) to register and slide to the bottom right corner of the lowest end

![](https://assets.bmyjacks.cn/img/20200309180434.png?x-oss-process=style/style)

{% endnote %}

After logging in, agree to the open source license, select the installation location, and you will be at the place of **select installation components**

![](https://assets.bmyjacks.cn/img/20200309180445.png?x-oss-process=style/style)


Here we expand the list and check the components as shown

![](https://assets.bmyjacks.cn/img/20200309180501.png?x-oss-process=style/style)


{% note warning %}
### Notice
If your computer system is **x86** version, please replace `MinGW 7.3.0 64-bit` with `MinGW 7.3.0 32-bit`
{% endnote %}

Click Next to start the installation

## At last
After installation, the Qt program appears in the start menu

![](https://assets.bmyjacks.cn/img/20200309180521.png?x-oss-process=style/style)


Click `Qt Creator 4.11.0 (Community)` to open the QtC page

![](https://assets.bmyjacks.cn/img/20200309180521.png?x-oss-process=style/style)

