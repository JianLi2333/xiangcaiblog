---
title: 如何使用VScode上传代码到github上
date: 2024-01-01 12:06:52
tags:
    - VScode
    - git
categories: 教程
description: 再也不用
---

# 如何使用VScode上传代码到github上

## 前言

每次写完我们的项目代码都需要在根目录下打开git bash，然后git add、git commit、git push，太麻烦了。VScode里面的插件可以帮我们简化这些步骤。我们只需要点点鼠标就OK了。

## 下载插件

![1704082411959](https://pic.xiangcaiblog.top/images/2024/01/01/202401011213865.png)

这个插件可以看到github仓库的提交记录等信息，还是挺方便的。

## 初始化本地仓库

首先需要做的就是初始化我们的本地仓库，这个仓库会用来暂存我们提交的代码。之前我们都是在根目录下打开git bash 然后使用git init来初始化本地仓库的。现在需要直接点两下就行了

![1704083545946](https://pic.xiangcaiblog.top/images/2024/01/01/202401011232307.png)

初始化仓库之后就会界面就会变成下面这个样子

![image-20240101123400791](https://pic.xiangcaiblog.top/images/2024/01/01/202401011234820.png)

## 连接远程仓库

本地仓库建好了之后就需要连接远程仓库了，之前我们都是直接在bash窗口中使用下面命令来连接远程库的

~~~bash
git remote add origin https://github.com/***/VSCode_Git_Test.git （这里是你的github仓库地址）
~~~

其中 origin是我们给这个远程库起的一个别名，不然每次都需要输入一长串地址太麻烦了。现在使用VScode更简单了。

![1704083929080](https://pic.xiangcaiblog.top/images/2024/01/01/202401011238930.png)

点击这个添加远程存储库

![image-20240101123951621](https://pic.xiangcaiblog.top/images/2024/01/01/202401011239642.png)

之后直接添加想要连接的远程存储库就行了，但是前提是你得先登录上github。

## 建立分支

![image-20240101125937649](https://pic.xiangcaiblog.top/images/2024/01/01/202401011259672.png)

![1704085288742](https://pic.xiangcaiblog.top/images/2024/01/01/202401011301897.png)

github上的仓库是有很多个分支的，这里可以选择本地分支和远程仓库的哪一个分支相连。这样我们一个项目可以建一个仓库，一个分支放后端代码，一个分支放前端代码。

## 提交代码

![image-20240101130358091](https://pic.xiangcaiblog.top/images/2024/01/01/202401011303123.png)

必须先点这个+号，将想要提交的文件添加到暂存区，这就相当于git add。之后点击提交，需要在上面写上messege。

## 推送

![image-20240101131654500](https://pic.xiangcaiblog.top/images/2024/01/01/202401011316552.png)

直接将代码推送到github上就ok了。

## 总结

VScode推送代码还是很方便的，但是也不要忘记了命令行工具的使用！

