---
title: Configure algolia search for NexT theme in hexo
tags:
  - hexo
  - NexT
  - algolia
  - search
categories:
  - NexT
keywords:
  - hexo
  - blog
  - next
  - algolia
description: After installing the NexT theme of hexo, let's take a look at how to configure algolia search
date: 2020-03-13 15:43:09
---

## First, we need to register an algolia account
Open [algolia's official website](https://www.algolia.com/)

![](https://assets.bmyjacks.cn/img/20200310184600.png?x-oss-process=style/style)

Click`FREE TRIAL`to register an account

![](https://assets.bmyjacks.cn/img/20200310205536.png?x-oss-process=style/style)

After filling in the corresponding email address and password, go to the console and create a new application:

![20200310205818](https://assets.bmyjacks.cn/img/20200310205818.png?x-oss-process=style/style)

Then select the location of the data storage, please choose the location according to your needs.

![20200310205938](https://assets.bmyjacks.cn/img/20200310205938.png?x-oss-process=style/style)

Then click `Create index` on the right to create the index name

![20200310211031](https://assets.bmyjacks.cn/img/20200310211031.png?x-oss-process=style/style)

This name must be remembered, it will be used later. For example, fill in `test` here, click `create`

![20200310211153](https://assets.bmyjacks.cn/img/20200310211153.png?x-oss-process=style/style)

After the creation is successful, find `API Keys` on the left

![20200310211303](https://assets.bmyjacks.cn/img/20200310211303.png?x-oss-process=style/style)

![20200310211356](https://assets.bmyjacks.cn/img/20200310211356.png?x-oss-process=style/style)

Save the API Key shown in the figure, and then we start to configure in hexo

## Configuration in hexo

We first install the algolia plugin

```bash
npm install hexo-algolia --save
```

Then configure in the **hexo's** config file

```yml
algolia:
  applicationID: 'Your applicationID'
  apiKey: 'Your Search-Only apikey'
  indexName: 'test(The name you used when creating the index above)'
```

![20200313153519](https://assets.bmyjacks.cn/img/20200313153519.png?x-oss-process=style/style)

Configure in **NexT's** config file

![20200313153620](https://assets.bmyjacks.cn/img/20200313153620.png?x-oss-process=style/style)

Set `enable` to `true`

## Upload the index to the algolia server
run

```bash
hexo clean
hexo algolia
```

If the following situation occurs

![20200313153947](https://assets.bmyjacks.cn/img/20200313153947.png?x-oss-process=style/style)

run
```bash
set HEXO_ALGOLIA_INDEXING_KEY=Your Admin apikey
hexo algolia
```

{% note success %}
## Congratulations
Congratulations to you，completed the installation and configuration of algolia!
{% endnote %}
