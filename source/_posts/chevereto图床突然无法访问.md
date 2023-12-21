---
title: chevereto图床突然无法访问
date: 2023-12-17 19:23:08
tags: 
	- 工具
	- 图床
categories: 教程
description: 搭建好的chevereto图床突然崩了！！！
---

# chevereto图床突然无法访问

## 前言

开始做一个项目，想写一篇博客记录一下，typora上传图片的时候一直上传失败，以为只是typora有抽风了，就想着直接使用picgo上传一下看看，结果也失败了。直接就慌了，不是我服务器出问题了吧？？？直接访问图床网址，好家伙，报错！！！这里不得不大骂一句，就没有人遇到过这种问题？百度和Google都翻遍了，全部是教你这么搭的！

## 解决方法

1. 先来看看报了什么错！

  ![image-20231217193238333](https://pic.xiangcaiblog.top/images/2023/12/17/202312171932365.png)

  上网查了一下，这句话告诉你出错了，但是你的debug等级不够，他不打印错误信息。

2. 然后需要在/app/settings.php文件中修改debug等级

  按照官方说法，
  0 无
  1 错误日志（默认）
  2 打印错误，没有错误日志
  3 打印和记录错误
  这里直接把模式调到3。

  ~~~PHP
  <?php
  $settings = array (
    'db_host' => 'localhost',
    'db_name' => 'pic_xiangcaiblog',
    'db_user' => 'pic_xiangcaiblog',
    'db_pass' => 'fKradMZhSdSz7Wfp',
    'db_table_prefix' => 'chv_',
    'db_driver' => 'mysql',
    'db_pdo_attrs' => 
    array (
    ),
    'debug_level' => 3,
  );
  ~~~

3. 在访问图床网址，就可以看到下面的信息

  ![image-20231217194210953](https://pic.xiangcaiblog.top/images/2023/12/17/202312171942999.png)

   大概意思就是找不到你数据库相关的某些文件。好好好，服务器的数据库停止运行了。重启一下，网站能正常使用了。

4. 为什么mysql会挂了？

	在/var/ log/messages文件夹中可以看到日志信息，翻了一下，出现下面的报错

	![image-20231217195802129](https://pic.xiangcaiblog.top/images/2023/12/17/202312171958158.png)

	很好！内存不够，没办法，服务器就2G内存，就这么用着吧，没钱！！！

	

	

