---
layout: post
title: pip install PIL 出现的问题方案
date: 2014-06-15 13:33:21
---

最近在Ubuntu里装PIL库时采用pip install PIL，发现出现Could not find any downloads that satisfy the requirement PIL的错误，导致安装不了，Google之，在stackoverflow发现有解决方案，原因是pip 在1.5版本升级有改动导致的问题。

解决办法：

安装方式改为：pip install PIL –allow-external PIL –allow-unverified PIL  完美解决！
