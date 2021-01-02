---
title: How to install Hexo
tags:
  - Hexo
  - GitHub
categories:
  - Hexo
keywords:
  - hexo
  - blog
  - hexo blog
  - github
description: Want to use Hexo to write a personal blog, but don't know how to start? This article will take you step by step to install Hexo to build your personal Hexo blog
date: 2020-02-09 15:49:20
---

![Hexo Logo](https://cdn.bmyjacks.io/img/20200309164643.png?x-oss-process=style/style)

## First, we need Git and Node.js
The installation of Git will not be demonstrated. I believe everyone who wants to use Hexo will install git.

### Below is the installation of Nodejs

Go to [node.js official website](https://nodejs.org/en/) to download.

Both the left and right can be downloaded, here is an example of the right:

![node.js download](https://cdn.bmyjacks.io/img/20200309164723.png?x-oss-process=style/style)

Next, we install node.js in the normal way.

After the installation is complete, enter `node -v` in the command line to view the node version, the installation is successful if the version number appears, as shown in the following figure:

![node version](https://cdn.bmyjacks.io/img/20200309165142.png?x-oss-process=style/style)

`npm -v` to view the npm version:

![npm version](https://cdn.bmyjacks.io/img/20200309165203.png?x-oss-process=style/style)

OK, we have installed node.js.

Next, we install Hexo. Enter `npm install hexo-cli -g` in the command line

Let's take a look at the meaning of this command:

`npm` is the most basic beginning part, `install` is the installation command, `hexo-cli` is the name of the package we want to install, and `-g` stands for global installation, which means you can use it anywhere The previously installed package. It is very important to understand the commands you enter, so that you have the opportunity to test the deployment on TravisCI in the future.

After clicking Enter, we saw a bunch of strange characters output from the command line. Leave him alone. Seeing these prompts indicates that your installation was successful:

![install Hexo](https://cdn.bmyjacks.io/img/20200309165221.png?x-oss-process=style/style)


## Next, create a new folder and install Hexo

We create a new folder with any name.

![create folder](https://cdn.bmyjacks.io/img/20200309165237.png?x-oss-process=style/style)


In the upper level folder, enter `hexo init <your folder name>` to initialize this folder:

![hexo initial](https://cdn.bmyjacks.io/img/20200309165254.png?x-oss-process=style/style)

Ok, now let's enter this folder and run `npm install` to install some dependent package files:

![npm install](https://cdn.bmyjacks.io/img/20200309165311.png?x-oss-process=style/style)

Then run `hexo generate` or `hexo g` (the two commands are actually the same) to initialize Hexo:

![hexo generate](https://cdn.bmyjacks.io/img/20200309165331.png?x-oss-process=style/style)

Then, enter `hexo server` or `hexo s` (the two commands are the same) to run Hexo web server locally:

![hexo server](https://cdn.bmyjacks.io/img/20200309165342.png?x-oss-process=style/style)

Now, open your browser, enter [`localhost:4000`](https://localhost:4000) in the address bar and press enter to enter the web page

![browser](https://cdn.bmyjacks.io/img/20200309165352.png?x-oss-process=style/style)

Well, we have successfully installed hexo


## Some common commands using Hexo

| intention                 | command                   |
| ------------------------- | ------------------------- |
| Create new draft          | `hexo new draft <name>`   |
| Publish the created draft | `hexo publish <name>`     |
| Create new page           | `hexo new page <name>`    |
| Generate website files    | `hexo generate`or`hexo g` |
| Start built-in web server | `hexo server`or`hexo s`   |
| Clean up generated files  | `hexo clean`              |
| `hexo clean` + `hexo g`   | `hexo g -f`               |

