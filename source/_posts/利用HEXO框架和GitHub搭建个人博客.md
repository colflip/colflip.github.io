---
title: 利用HEXO框架和GitHub搭建个人博客
mathjax: true
tags:
  - 教程
  - Hexo
  - NexT
  - GitHub
  - Freenom
categories: 专业知识
date: 2018-10-31 14:24:16
---
Hexo 是一个简单地、轻量地、基于Node的一个静态博客框架，可以方便的生成静态网页托管在GitHub和Heroku上。基本原理是用Git将hexo博客在本地编译后的文件，上传到GitHub，通过地址访问。通过此种方法看到的，严格上并不是一个网站系统，而只是托管在GitHub上的一堆静态网页。但我们可以在本地更新后，同步到GitHub来实现和网站系统一样的功能。

## 环境准备

### 本地环境准备

下载并安装Git

下载并安装Node.js

### 账号注册

注册GitHub账号

## 建站过程

以下过程在Git中进行。

### 安装hexo

``` bash
$ install hexo
```

### 本地调试

``` bash
$  hexo clean;//清理
$  hexo generate;//编译
$  hexo sever;//开启本地服务
```

打开浏览器，通过http://localhost:4000访问。

### 在GitHub上创建存储库

命名方式为：用户名.github.io。

### 修改 站点配置 文件_config.yml

``` bash
  deploy:
    type: git
    repo: https://github.com/用户名/用户名.github.io
    branch: master
```

###  部署到GitHub

第一次可能需要登录GitHub账户。

``` bash
$  hexo deploy;//部署
```

### 访问

通过 https://用户名.github.io 访问。

## 功能拓展

### 更改主题

可以再hexo官网查找主题，本站使用了[next](https://github.com/theme-next/hexo-theme-next) 主题。

### 启用本地搜索

安装

``` bash
$  npm install hexo-generator-searchdb --save   
```

修改 站点配置 文件_config.yml

``` bash
search:
  path: search.xml
  field: post
  format: html
  limit: 10000
```

修改 主题配置文件

``` bash
local_search:
  enable: true
```

### 第三方评论

可以使用LiveRe(来必力)等。

### 网站统计

可以使用百度统计等。

### 更改访问域名

 可以在github项目库setting中设置自己的域名。

 在freenom.com 可以注册.ml, .tk等结尾的免费顶级域名。

## 博文撰写

 可以用符合Markdown语法的软件写自己的博客。
