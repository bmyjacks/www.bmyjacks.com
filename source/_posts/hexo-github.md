---
title: Upload your hexo blog to GitHub
tags:
  - hexo
  - GitHub
  - blog
categories:
  - hexo
description: This article describes how to upload hexo blog to GitHub
keywords:
  - hexo
  - git
  - github
  - blog
  - blogger
date: 2020-03-16 15:27:56
---

## Method 1: Use hexo plugin to upload automatically
### Create GitHub repository
First, we create a new GitHub repository

![20200316150827](https://assets.bmyjacks.cn/img/20200316150827.png?x-oss-process=style/style)

![20200316150902](https://assets.bmyjacks.cn/img/20200316150902.png?x-oss-process=style/style)

modify config.yml

Open the configuration file of hexo. The default` http://yoursite.com ` replace with your own URL

![20200316151051](https://assets.bmyjacks.cn/img/20200316151051.png?x-oss-process=style/style)

Replace `deploy` at the bottom of the configuration file with
```yml
deploy:
    type: git
    repo: #Your GitHub repository address,such as https://github.com/yourname/yourrepo.git
    branch: master
```

Install plugin
```bash
npm install hexo-deployer-git --save
```

deploy
```bash
hexo g && hexo d
```

You can then visit your website to view the hexo blog

## Method 2: manually upload the entire folder
Command line input
```bash
git init
```

Fill in the following in the newly generated '.gitignore'
```txt
.DS_Store
Thumbs.db
db.json
*.log
node_modules/
public/
.deploy*/
```

![20200316152215](https://assets.bmyjacks.cn/img/20200316152215.png?x-oss-process=style/style)

Add remote repository
```bash
git remote add origin https://github.com/yourname/yourrepo.git
```

push
```bash
git push -u origin master
```

{% note success %}
## Congratulations
Congratulations to you，successfully uploaded hexo blog to GitHub！
{% endnote %}
