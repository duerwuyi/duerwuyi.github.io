---
title: idea配置python环境、运行github上django项目保姆级教程
toc: true
date: 2022-02-21 13:45:36
author: Duerwuyi
tags: [intellij idea,python,Django]
categories: [python,Django]
cover: https://duerwuyi.github.io/2022/02/21/idea-python-django-bulid/Djangoimg2.png
thumbnail: https://duerwuyi.github.io/2022/02/21/idea-python-django-bulid/Djangoimg.png
---
假期在家接了一个项目，后端是用Django框架完成的，到学校换了电脑，需重新配置环境。由于不想装pycharm，因此基本一个idea解决所有问题。

<!-- more -->

## 下载和安装

idea请自备。python我选择直接下载anaconda3，使用里面的python。理论上不建议同时安装python3本体和anaconda，会引发命令行python指向不明确的问题。安装时要勾选添加环境变量，漏了建议重新安装。

![python成功安装](python1.png)

随后升级pip。anaconda自带的pip版本比较低。如果遇到https错误请换阿里源或挂梯。

``` cmd cmd
python -m pip install --upgrade pip
```

安装Django。

``` cmd cmd
pip install Django
```

使用豆瓣源请使用：

``` cmd cmd
pip install Django -i http://pypi.douban.com/simple --trusted-host pypi.douban.com
```

## 配置

idea搜索插件python并安装。

![python插件](idea1.png)

进入新项目 File->New->project from version control ，从远程github上爬取新项目。

![项目初始样子](proj1.png)

这一步格外重要：idea默认把新项目识别为JAVA项目，因此要在.idea/项目名.iml文件中修改，将JAVA改为PYTHON。

![修改](proj2.png)


然后打开File -> project structure -> SDK 创建新的python sdk。注意勾选并选择python默认编辑器。

![两项都要勾选](proj3.png)

再配置此项目的SDK。

![Project](proj4.png)

再在facets里填入setting.py。

![Project](proj8.png)

随后等待右下方的update。最后点击右下角Event Log，configure一下Django项目。

再点击tool bar上的add configuration，或者是run->edit configuration。

![Project](proj5.png)

打开manage.py，看到这一行：

![Project](proj6.png)

把这个变量的值添加到configuration里的环境变量当中。

![Project](proj7.png)

进入虚拟环境，输入：

``` cmd cmd
 venv\Scripts\activate
 pip freeze > requirement.txt
 pip install -r requirement.txt
 #上一步出错就先执行pip install mesa
```

最后把剩下几个没装好的包手动装一下即可。

## 完成

点击启动，可以看到命令行成功：

![启动时的命令行](proj9.png)

用postman测一下：

![postman](proj10.png)

成功返回。至此，部署完成。

