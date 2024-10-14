---
title: Hexo
date: 2018-02-12 16:14:26
tags:
  - Hexo
categories:
  - 其他技术
cover: /imgs/img1.jpg
toc: true
---

Hexo 是基于 Node.js 的静态站点生成器,本文记录常用Hexo命令, 以及一些常用配置。

<!-- more -->

# 全局安装

```bash
npm install -g hexo-cli
```

# 初始化

```bash
hexo init blog
cd blog
npm install
```

# 本地预览

```bash
hexo server
```

# 新建文章

```bash
hexo new "新文章"
```

# 生成静态文件

```bash
hexo generate
```

# 部署

```bash
hexo deploy
```

# 更多

- [Hexo文档](https://hexo.io/zh-cn/docs/index.html)
