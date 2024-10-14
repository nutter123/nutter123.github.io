---
title: SEO优化
date: 2019-04-17 15:18:26
tags:
  - 前端优化
categories:
  - 前端
cover: /imgs/img6.jpg
toc: true
---

前端的SEO优化方案

<!-- more -->

## [](#HTML页面 "HTML页面")HTML页面

1.  合理的title、description、keywords：搜索对着三项的权重逐个减小，title值强调重点即可；description把页面内容高度概括，不可过分堆砌关键词；keywords列举出重要关键词。
2.  语义化的HTML代码，符合W3C规范：语义化代码让搜索引擎容易理解网页
3.  重要内容HTML代码放在最前：搜索引擎抓取HTML顺序是从上到下，保证重要内容一定会被抓取
4.  重要内容不要用js输出：爬虫不会执行js获取内容
5.  少用iframe：搜索引擎不会抓取iframe中的内容
6.  非装饰性图片必须加alt
7.  提高网站速度：网站速度是搜索引擎排序的一个重要指标

## [](#前后端分离页面 "前后端分离页面")前后端分离页面

1.  使用prerender.原理是将渲染完的页面再返回给爬虫工具.
2.  先去 [https://www.baidu.com/robots.txt](https://www.baidu.com/robots.txt) 找出常见的爬虫，然后在nginx上判断来访问页面用户的User-Agent是否是爬虫，如果是爬虫，就用nginx方向代理到我们自己用nodejs + puppeteer实现的爬虫服务器上，然后用你的爬虫服务器爬自己的前后端分离的前端项目页面，增加扒页面的接收延时，保证异步渲染的接口数据返回，最后得到了页面的数据，返还给来访问的爬虫即可。
