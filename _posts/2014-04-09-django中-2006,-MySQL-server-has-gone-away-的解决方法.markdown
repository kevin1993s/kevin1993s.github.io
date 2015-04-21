---
layout: post
title: "django中 2006, MySQL server has gone away 的解决方法"
date: 2014-04-09 15:23:55
---

django models中自带了数据库模型，只需在对应的app下的models.py里建立class集成model就能够在其他地方import进来使用了，对象方法比较多，关系型数据库中常用的诸如select update insert delete等语句都能够有对应的函数实现。但是有此基于mysql数据库时，在一个sleep语句（sleep时间较长）之后，再使用数据库对象操作的时候，直接回显出2006, ‘MySQL server has gone away’的错误了。解决方案如下:

首先我在/etc/mysql/my.cnf文件中的[mysqld]字段下增加了：

    wait_timeout = 10
    interactive_timeout = 10

但是发现还是显示gone away的错误。然后再操作数据库之前添加：

    import django.db
    django.db.close_connection()

然后再次执行，发现能够操作数据库了，错误也没有了。
