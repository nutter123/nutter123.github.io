---
title: bug处理-零宽度字符
date: 2020-06-10 12:11:26
tags: 
- 前端开发
- 前端bug
categories:
- 前端
cover: /imgs/img2.jpg
thumbnail: /imgs/img2.jpg
toc: true
---

一种不可打印的Unicode字符,在浏览器等环境下不可见,会导致解析异常.

<!-- more -->

## 问题背景

商家小程序

## 问题描述

后端返回数据中存在零宽度字符,导致解析异常.

## 原因

1. 一种不可打印的Unicode字符,在浏览器等环境下不可见.
2. 在js中应用为数据防爬和信息携带.

## 解决方法

```javascript
str.replace(/[\u200b-\u200f\uFEFF\u202a-\u202e]/g, "");
str.replace(/[^\u200b-\u200f\uFEFF\u202a-\u202e]/g, "");
```

