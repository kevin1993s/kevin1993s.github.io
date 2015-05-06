---
layout: post
title: "[转]Django中集成cron"
date: 2015-05-06 15:21:22
---

在linux上有神器cron，它以job的方式定时执行sheell命令或者程序。有的时候在web应用中也有在后台执行定时任务的需求，例如起一个daily job去更新数据库或者做一个data fix什么的。有人也为Django写了一个集成cron的库 - django-crontab。

##### 安装

从pip安装：

    pip install django-crontab

##### 设置

在settings中将app加入installed_apps：

    INSTALLED_APPS = (
    'django_crontab',
    ）)

在settings中设置cron job。第一个参数是标准的cron时间设定，第二个参数是你执行函数的路径（注意从app根目录写起）：

    CRONJOBS = [
        ('0 0 * * *', 'yourapp.to.yourjob') // 每天0点运行
            ('*/1 * * * *', 'yourapp.to.yourjob') // 每分钟运行一次
            ]


