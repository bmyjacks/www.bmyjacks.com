---
title: Using Arduino IDE to configure esp8266 development environment
tags:
  - esp8266
  - arduino
  - helloworld
categories:
  - esp8266
description: How to configure the development environment under Arduino after purchasing the esp8266 development board? Let's study together!
keywords:
  - esp8266
  - arduino
hide: false
date: 2020-08-13 09:29:29
---


## Download and install Arduino IDE
First go to [Arduino official website](https://www.arduino.cc/)，go[download IDE](https://www.arduino.cc/en/Main/Software)

Slide down to

![Download arduino](https://cdn.bmyjacks.io/img/20200813090226.png?x-oss-process=style/style)

Click 'Windows Installer' in the page to download the installation program

{% note info %}
### info
Please download the corresponding **IDE version** according to your **actual needs**, such as `Windows app` for `UWP` version and `Linux arm 32 bits` for `Raspberry Pi`。
{% endnote %}

After the download is completed, run the installation program and allow the user account control to install the program as usual.

## Configuring the esp8266 environment
### Method 1
Click`Files>Preferences`or press`Ctrl + ,(comma)`

![](https://cdn.bmyjacks.io/img/20200813091825.png?x-oss-process=style/style)

Fill `Additional development board manager website` column with `http://arduino.esp8266.com/stable/package_esp8266com_index.json`

Click “OK” to save it，then go to `Tools>development board>development board manager`，search `esp8266`

![](https://cdn.bmyjacks.io/img/20200813092116.png?x-oss-process=style/style)

Install the corresponding development board to complete the configuration of the esp8266 development environment.

### Method 2
Go to folder `Arduino>hardware`，Create a new folder called `esp8266com`，enter it and open cmd
```bash
git clone https://github.com/esp8266/Arduino.git esp8266
cd esp8266
git submodule update --init
cd tools
python3 get.py #The last step of python execution is not prompted
```

After these steps are completed, restart Arduino IDE and select esp8266 in the development board.
