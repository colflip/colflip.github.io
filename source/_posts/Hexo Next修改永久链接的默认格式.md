---
title: Hexo Next修改永久链接的默认格式
mathjax: true
tags:
  - Web
  - Hexo
  - NexT
categories: 编程开发
date: 2019-04-01 10:52:50
---
# 方法一
## 安装插件
``` bash
npm install hexo-abbrlink --save
```

## 修改站点配置文件
``` bash
# permalink: :year/:month/:day/:title/
# permalink_defaults:
permalink: posts/:abbrlink.html
abbrlink:
  alg: crc32  # 算法：crc16(default) and crc32
  rep: hex    # 进制：dec(default) and hex
```
修改完成后，文章链接变成 /posts/xxxxx.html的形式，避免中文带来的问题，和有利于搜索引擎的抓取。
# 方法二
https://hexo.io/zh-cn/docs/permalinks.html
