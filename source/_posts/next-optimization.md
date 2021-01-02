---
title: NexT theme speed optimization
tags:
  - NexT
  - Hexo
categories:
  - NexT
description: Blogs using NexT themes open slowly? Let’s take a look at how to optimize your blog!
keywords:
  - NexT
  - hexo
  - blog
  - optimization
date: 2020-04-06 11:21:03
---

## config.yml optimization that comes with Hexo
Changing lines 21-23 of the link configuration file of the original theme to the following file will help SEO

```yml
url: https://www.bmyjacks.com #Fill in your website address
root: / #Fill in your root directory address
permalink: :year/:title.html #Suggest to change to this
```

## NexT theme `_config.next.yml` optimization
There are more options for this one, let me talk about it carefully

### Open cache and minimize
```yml
cache:
  enable: true

minify: true
```

### favicon optimization
The favicon icon file is preferably compressed and stored in such as `Fastly cdn` etc.

Line 39~45
```yml
favicon:
  small:
  medium:
  apple_touch_icon:
  safari_pinned_tab:
  #android_manifest:
  #ms_browserconfig:
```

Line 159~166
```yml
# Sidebar Avatar
avatar:
  # Replace the default image and set the url here.
  url: https://assets.bmyjacks.cn/icons/android-chrome-144x144.png?x-oss-process=style/icon
  # If true, the avatar will be dispalyed in circle.
  rounded: false
  # If true, the avatar will be rotated with the cursor.
  rotated: false
```

## Turn off some unnecessary functions
This optimization method varies from person to person, please choose according to your needs

### Close animation
After turning off the animation, there is no transition animation displayed on your website. Please consider and change lines 823-833

```yml
motion:
  enable: false
  async: false
  transition:
    # Transition variants:
    # fadeIn | flipXIn | flipYIn | flipBounceXIn | flipBounceYIn
    # swoopIn | whirlIn | shrinkIn | expandIn
    # bounceIn | bounceUpIn | bounceDownIn | bounceLeftIn | bounceRightIn
    # slideUpIn | slideDownIn | slideLeftIn | slideRightIn
    # slideUpBigIn | slideDownBigIn | slideLeftBigIn | slideRightBigIn
    # perspectiveUpIn | perspectiveDownIn | perspectiveLeftIn | perspectiveRightIn
    post_block: fadeIn
    post_header: slideDownIn
    post_body: slideDownIn
    coll_header: slideLeftIn
    # Only for Pisces | Gemini.
    sidebar: slideUpIn
```

### Reduce unnecessary services
If you have set up two comment systems, please remove one when optimizing and leave only the most suitable one.

Close the online chat, close the online chat system such as `chatra`

### Disable pace
```yml
pace:
  enable: false
  # Themes list:
  # big-counter | bounce | barber-shop | center-atom | center-circle | center-radar | center-simple
  # corner-indicator | fill-left | flat-top | flash | loading-bar | mac-osx | material | minimal
  theme: minimal
```

### Disable three
```yml
three:
  enable: false
  three_waves: false
  canvas_lines: false
  canvas_sphere: false
```
### Use CDN
Now the NexT theme has its built-in CDN. No manual adjustment required
