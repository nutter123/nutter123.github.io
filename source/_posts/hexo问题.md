---
title: Hexo-问题总结
date: 2018-03-12 14:14:26
tags: [Hexo]
toc: true
---

在搭建Hexo博客的过程中遇到了一些问题，本文记录一些问题及解决方法。

<!-- more -->

# 一.环境搭建问题

## 1.安装node.js

## 2.安装git

```
配置账户
$ git config --global user.name “your_username” #设置用户名
$ git config --global user.email “your_registered_github_Email” #设置邮箱地址(建议用注册giuhub的邮箱)  

关联远程库
$ git remote add origin git@github.com:nutter123/nutter123.github.io.git
```

## 3.创建github新远程库

> 在添加远程库时，由于本地之前已经添加了公司的远程库，在重新注册了账户之后，公司远程由于输错了密码一直无法提交代码。  
> 解决方法：  
> 进入控制面板\\所有控制面板项\\凭据管理器中 将windows凭据中找到公司远程库，删除信息

# 二.hexo命令

> hexo init –初始化hexo环境,这时会在目录下自动生成hexo的文件  
> hexo generate –生成静态页面  
> hexo server –生成本地服务(hexo s –debug 调试模式)  
> hexo deploy –部署我们的个人博客  
> hexo clean –清除缓存

```
每次部署步骤：
hexo new "hello word"
hexo clean 
hexo g 
hexo d
```

# 三.连接本地和GitHub

> 打开\_config.yml进行编辑,翻到文件最下方，将deploy的选项改成以下的形式，并将yournmae修改为你自己的名称:

```
deploy:
type: git
repo: git@github.com:yourname/yourname.github.io.git
branch: master 
```

> 然后在GitBash中执行

```
npm install hexo-deployer-git --save
```

> 最后执行 hexo deploy
