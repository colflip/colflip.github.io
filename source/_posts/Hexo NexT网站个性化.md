---
title: Hexo NexT网站个性化
mathjax: true
tags:
  - Web
  - Hexo
  - NexT
categories: 编程开发
date: 2019-03-06 22:14:49
---

## 添加字数统计、阅读时长

适用于next 6 以后版本，分两步完成

 1. 安装 npm install hexo-symbols-count-time --save
 2. 主配置文件（根hexo目录） 添加
   
 ``` bash
 symbols_count_time:
  symbols: true
  time: true
  total_symbols: true
  total_time: true
```

## 添加404公益界面

创建页面，在 Hexo 文件夹根目录下 /source/404/index.html；

 ``` bash
 ---
 title: 404 Not Found：该页无法显示
 toc: false
 comments: false
 permalink: /404
 ---
 <!DOCTYPE html>
 <html>
     <head>
          <meta charset="UTF-8" />
          <title>404</title>                                                                                                                                        
     </head>
     <body>
          <script type="text/javascript" src="//qzonestyle.gtimg.cn/qzone/hybrid/app/404/search_children.js" homePageName="返回首页" homePageUrl="https://yohua.ml"></script>
 	</body>
 </html>
```

部署

 ``` bash
hexo d -g
```

## 添加网易云音乐

在网易云音乐生成外链，将代码放置合适位置即可。

``` bash
<iframe frameborder="no" border="0" marginwidth="0" marginheight="0" width=330 height=46 src="//music.163.com/outchain/player?type=2&id=25638273&auto=0&height=46"></iframe>
```

## 首页隐藏部分文章

### 方法一

使用插件hexo-generator-index2。

安装hexo-generator-index2

``` bash
$ npm install hexo-generator-index2 --save
$ npm uninstall hexo-generator-index --save
```

修改hexo的配置文件

``` bash
# index2 generator是否包含官方的hexo-generator-index，默认true（包含）
index2_include_index: true # defult is true

# 配置index2 generator，可以是数组或对象
index2_generator:
  per_page: 10
  order_by: -date
  include:
    - category Web # 只包含Web分类下的文章
  exclude:
    - tag Hexo # 不包含标签为Hexo的文章
```

插件链接：https://github.com/Jamling/hexo-generator-index2/blob/master/README_zh.md

### 方法二

使用另一个插件，效果更好，可以同时对归档的目录隐藏。插件地址:https://github.com/printempw/hexo-sage-posts

## 在移动设备下启用NexT主题的目录页面和回到顶部按钮

https://leaferx.online/2017/02/05/EnableTOConMobile/
