---
title: 利用onedrive搭建自己的私有云盘
date: 2023-11-14 14:56:11
tags: onedrive
categories: 教程
description: 百度网盘请保持距离，我怕onedrive误会！
cover: https://pic.xiangcaiblog.top/images/2023/11/19/202311191602287.png
---

#  利用onedrive搭建自己的私有云盘

## 前言

之前研究搭建个人图床的时候，研究了一下onedrive。本来想着用它来搭建图床的，但是好像没有那么方便，在picgo上没有找到相应的插件。不过，一个T容量的onedrive用起来真的是非常的香了。之前还写过教程，在另一台电脑上想更新自己的博客可以克隆github上的博客源码，然后再操作。这有了onedrive就方便很多了。只要将博客源码保存在onedrive中就行了，只要是windows的电脑登上onedrive就能写了。什么东西都是配置好了的。当然，这篇文章主要是教如何使用onedrive搭建自己的私有云盘。百度网盘之类的第三方网盘我只能说懂得都懂。用不了一点。速度大于1M/s娘的都得怀疑一下自己是不是手抖开了一个SVIP😅

虽然网上也有人说onedrive的速度感人，但是我个人实验起来速度稳定大于3M/s。可能是我这的网好一点(?_?)，但是百度网盘依旧稳定发挥。

## 配置github

1. 将[onedrive-vercel-index](https://github.com/spencerwooo/onedrive-vercel-index)导入自己的仓库，并设置为私人仓库

	![1700220786747](https://pic.xiangcaiblog.top/images/2023/11/17/202311171934292.png)

2. 修改源码中的/config/site.json文件

	![1700221234173](https://pic.xiangcaiblog.top/images/2023/11/17/202311171940611.png)

3. 登录Azure Active注册应用

	![1700221402547](https://pic.xiangcaiblog.top/images/2023/11/17/202311171943752.png)

	![1700221474927](https://pic.xiangcaiblog.top/images/2023/11/17/202311171944649.png)

	![1700221976845](https://pic.xiangcaiblog.top/images/2023/11/17/202311171953646.png)

	![1700222119127](https://pic.xiangcaiblog.top/images/2023/11/17/202311171955975.png)

4. [加密客户端密码](https://www.dute.org/aes)

	![1700222450197](https://pic.xiangcaiblog.top/images/2023/11/17/202311172000747.png)

5. 修改/config/api.json文件

	![1700222189210](https://pic.xiangcaiblog.top/images/2023/11/17/202311171956376.png)

6. 添加API权限

	![1700222594010](https://pic.xiangcaiblog.top/images/2023/11/17/202311172003269.png)

	![1700222634855](https://pic.xiangcaiblog.top/images/2023/11/17/202311172004722.png)

	## 配置vercel

	1. 导入自己的onedrive-vercel-index仓库

		![](https://pic.xiangcaiblog.top/images/2023/11/17/202311172008650.png)

	2. 登录upstash(https://upstash.com/)创建一个Redis数据库

		![image-20231117201142872](https://pic.xiangcaiblog.top/images/2023/11/17/202311172011907.png)

		![image-20231117201208446](https://pic.xiangcaiblog.top/images/2023/11/17/202311172012475.png)

	3. 配置vercel环境参数

		![1700223300174](https://pic.xiangcaiblog.top/images/2023/11/17/202311172015984.png)

		![1700223971076](https://pic.xiangcaiblog.top/images/2023/11/17/202311172027801.png)

		![202311172029162](https://pic.xiangcaiblog.top/images/2023/11/17/202311172029162.png)

		![1700224192384](https://pic.xiangcaiblog.top/images/2023/11/17/202311172030553.png)

		![1700224456693](https://pic.xiangcaiblog.top/images/2023/11/17/202311172034466.png)

	4. 配置私密文件夹密码

		![1700224563435](https://pic.xiangcaiblog.top/images/2023/11/17/202311172036066.png)

		## 结束

		之后只要将想要分享出来的文件放在onedrive的public文件夹中就行了。通过访问vercel的项目的域名就可以在线访问到相应的资源了。当然可以更换一个自己的二级域名。可以看看[香菜的私人网盘](https://onedrive.xiangcaiblog.top/zh-CN/)
