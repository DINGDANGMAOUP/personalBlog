title: k8s+docker+harbor+jenkins+sonarqube搭建方案
author: kuroneko
tags:
  - k8s
  - docker
  - harbor
  - jenkins
  - sonarqube
categories:
  - 持续集成
date: 2020-11-16 13:26:00
---
DevOps (一)
---

##### 一,环境准备

|      ip           | hostname| centos | remark |
| :-----------: | :-----------:  | :--------: |:---------:|
| ------------  | master69 |  7.8        | master node ，nfs|
| ------------  | node125   |  7.8        |worker node|
| ------------  |  node14    |  7.8         |worker node|
|------------   |node194   |   7.8        |harbor|
|------------   |node79      |    7.8      |elkb|


##### 二,软件版本

+ Kubernetes v1.19.4
+ Docker v19.03.12
+ Harbor v2.1.1
+ elkb v?(<font color=red>待定</font>)


+ [<font color=blue>k8s架构图</font>](https://www.kubernetes.org.cn)
![k8s](https://www.kubernetes.org.cn/img/2016/10/20161028141542.jpg "k8s架构")