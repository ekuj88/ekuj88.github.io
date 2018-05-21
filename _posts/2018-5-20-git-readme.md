﻿---
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
#GitHub教程
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
Git为Windows用户提供极简化版的Linux命令行窗口，用于执行GitHub相关命令。
🐵下载地址：[https://git-scm.com/downloads](https://git-scm.com/downloads)
![Alt text](http://blog.iv1.xin/img/180520/01.jpg)
![Alt text](http://blog.iv1.xin/img/180520/02.jpg)
![Alt text](http://blog.iv1.xin/img/180520/03.jpg)
![Alt text](http://blog.iv1.xin/img/180520/04.jpg)
![Alt text](http://blog.iv1.xin/img/180520/05.jpg)
![Alt text](http://blog.iv1.xin/img/180520/06.jpg)
![Alt text](http://blog.iv1.xin/img/180520/07.jpg)

### 创建项目工作区
#### 创建目录
##### 初始化项目工作区
##### 工作区内日常文件操作
创建、修改、删除文件
### git普通流程操作
#### 添加工作区里的文件到暂存区
#### 查看暂存区文件状态
未添加到暂存区的新文件
未添加到暂存区的状态为已经修改、已经删除的文件
暂存区里已经更新，等待提交到本地版本库的文件
#### 撤销已添加到暂存区的文件

备注：不会改变工作区文件

```
git reset HEAD filename.ext
```

#### 将暂存区的里待提交的文件，提交到本地版本库
#### 将本地版本库文件，提交到github线上
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