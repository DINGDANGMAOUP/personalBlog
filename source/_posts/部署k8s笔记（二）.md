---
title: 部署k8s笔记（二）
author: kuroneko
tags:
  - docker
  - 非root用户
categories:
  - linux
  - k8s
abbrlink: 55650
date: 2020-12-03 15:37:00
---
安装docker后为了方便非root用户不带sudo运行docker指令作如下操作
```
#该操作一般安装docker时都帮你操作了，以防万一先记录
sudo groupadd docker    
#将当前用户加入docker组
sudo gpasswd -a $USER docker
#更新组策略
newgrp docker     
```
之后
```
logout
```
或注销退出当前用户（我是本机操作QAQ，）