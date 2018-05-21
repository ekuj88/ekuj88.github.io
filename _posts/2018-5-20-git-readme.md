---
layout: post
title:  "GitHub教程"
categories: Tutorial
tags:  GitHub Tutorial
author: iv1
mathjax: true
date:   2016-12-8 15:14:54
---

* content
{:toc}
GitHub是最顶尖的代码版本管理工具之一，支持个人离线、团队在线协作的版本管理工具。本文简要讲解它的使用方法。



`本教程格式的约定：`
- `标注🐵符号，需要自己进行探索性操作，才能理解的知识点`
- `标注🐶符号，需要牢记的操作`
- `标注🐯符号，重要的知识点`
- `标注🍸符号，是额外的知识`
## 注册GitHub账号

* 进入[GitHub官网：https://github.com](https://github.com/)，免费注册账号。
* 登录官网，🐵在线添加新的仓库，使用默认选项。“仓库”叫做Repositories。每个开发项目都以仓库为单位进行版本管理。
* 免费版的代码仓库中的代码是对所有人公开的、只读的，需要你的授权才能修改。普通项目免费版功能完全够用了。收费版可以完全保密，每月7美元。

## Windows系统下Git环境的部署

### 安装 git 
在本地安装 git，它为Windows用户提供git环境，以及相关管理工具。我们主要使用其中的Git Bash。

🐵下载地址：[https://git-scm.com/downloads](https://git-scm.com/downloads)

在安装过程中，有好多选项，请注意查看。后期使用中出错，极有可能是由于安装时的选项有关。以下是安装截图。

![第1步](http://blog.iv1.xin/img/180520/01.jpg)
![第2步](http://blog.iv1.xin/img/180520/02.jpg)
![第3步](http://blog.iv1.xin/img/180520/03.jpg)
![第4步](http://blog.iv1.xin/img/180520/04.jpg)
![第5步](http://blog.iv1.xin/img/180520/05.jpg)
![第6步](http://blog.iv1.xin/img/180520/06.jpg)
![第7步](http://blog.iv1.xin/img/180520/07.jpg)

### 创建项目工作区

在本地创建一个文件夹，并用git初始化后，此文件夹就是项目文件的工作区。和普通文件夹使用没什么区别，正常存放项目文件即可。

#### 创建目录

windows开始菜单 点击运行 Git Bash 。Git Bash类似于linux shell的命令行环境，我们主要使用它操作github的常用功能。
命令如下：（命令执行后，默认不显示结果，就是成功了。）
```bash
$ cd /d/git  #进入d盘，更换当前盘符，注意cd后面有空格
$ mkdir myfolder #创建目录 
$ cd myfolder #进入目录
# rm 文件名 #删除文件
# rm 目录名 -r  #删除目录
```

#### 初始化目录，成为项目工作区

```bash
$ cd /d/git/myfolder
$ git init #🐶
Initialized empty Git repository in D:/git/myfolder/.git/
$ ls -lah #可以看到显示增加了 .git 隐藏目录 git的相关配置文件
```

#### 在工作区里操作文件
使用windows下的开发软件，把文件存储到工作区目录。或者直接使用Git Bash创建一个。
```bash
vim first_program.py
```
i #插入文字 Esc :wq #保存（vim是一个常用编辑器。只能帮你到这了）

至此，git版本管理工具，可以管理的一个项目目录工作区，创建好了。

## git基本操作

将工作区里的项目文件，提交到版本管理工具的基本操作。

### 工作区里的文件添加到暂存区

暂存区：可以把当前工作区的数据进行暂时存储，类似于快照。
在工作区目录中，添加所有文件（注意是：空格点），也可以添加单个文件，命令如下：
```
$ git add .
$ # git first_program.py
```
#### 查看暂存区文件状态
一般是分批添加到暂存区，所以要查看当前已经添加和未添加的文件。
由于添加与未添加有时间差，所以要查看暂存区与工作区文件的区别，

```
$ git status #🐶
```

未添加到暂存区的新文件
未添加到暂存区的状态为已经修改、已经删除的文件
暂存区里已经更新，等待提交到本地版本库的文件


![第1步](http://blog.iv1.xin/img/180520/11.jpg)
![第2步](http://blog.iv1.xin/img/180520/12.jpg)
![第3步](http://blog.iv1.xin/img/180520/13.jpg)
![第4步](http://blog.iv1.xin/img/180520/14.jpg)
![第5步](http://blog.iv1.xin/img/180520/15.jpg)

#### 撤销已添加到暂存区的文件

将暂存区的文件撤销，不会改变工作区文件

```
git reset HEAD filename.ext
```

#### 将暂存区的里待提交的文件，提交到本地版本库
```
$ git commit -m '关于此次提交的描述'#🐶
```

#### 将本地版本库文件，提交到github线上

```
$ git origin#🐶
```

### git进阶操作
##### 将暂存区文件还原到工作区

文件已经添加到暂存区，但未提交到本地版本库时。修改了工作区文件，想要从暂存区里还原到回来。

```
git checkout 文件名
```

备注：同一文件在工作区无论修改几次,都将以最后一次提交到暂存区时为准。

##### 查看版本日志
##### 工作区文件回滚到上一版本
##### 工作区文件回滚到任意版本
##### 暂存区与本地版本仓库区别
git diff：是查看工作区与暂存区的差别的。

git diff --cached：是查看暂存区与版本仓库的差别的。

git diff HEAD：是查看working tree和commit的差别的。（HEAD代表的是最近的一次commit的信息）