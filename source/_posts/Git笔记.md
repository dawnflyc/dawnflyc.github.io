---
title: Git笔记
categories:
  - 技术
tags:
  - git
description: git命令笔记
abbrlink: 5bd9b965
date: '2021-05-10 10:36:01'
---

######   初始化

```console
git config --global user.name ""
git config --global user.email ""
```

--global  全局，只需要执行一次。



###### 如何开始

有一个尚未进行版本控制的项目，想用git控制它。

```
git init
```

初始化，会生成.git目录。



###### 克隆仓库

```console
git clone https://github.com/*
```

或者将克隆数据，存放到目录

```
git clone https://github.com/* 目录
```

或者想克隆某个分支

```
git clone https://github.com/* -b *
```



###### 新增跟踪文件

``` csharp
git add 文件
```

跟踪文件

```
git add --all 文件
```

跟踪所有增删改



###### 分支 

```ruby
git branch *
```

创建分支

###### 提交

```
commit -m ""
```



###### 远程仓库

```
git remote add 别名 https://github.com/*.git
```



###### 推送

```
git push 别名 分支
```



###### 更多

https://www.jianshu.com/p/93318220cdce

https://www.runoob.com/git/git-tutorial.html

https://git-scm.com/book/zh/v2



github 提示:



新建仓库:

```
echo "# ****" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/dawnflyc/*.git
git push -u origin main
```

推送现有:

```
git remote add origin https://github.com/dawnflyc/*.git
git branch -M main
git push -u origin main
```

