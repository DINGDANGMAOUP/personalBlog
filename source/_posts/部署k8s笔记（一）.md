title: 部署k8s笔记（一）
author: kuroneko
tags:
  - k8s
  - kubernetes
categories: linux
abbrlink: 18712
date: 2020-11-16 10:16:00
---
#### 前言
由于公司给定了不同网段linux服务器（centos7.8）
###### 产生的问题
当输入 
```
kubectl get nodes
```
出现了以下问题
```
The connection to the server localhost:8080 was refused - did you specify the right host or port?
```
针对此问题的解决方案
将<font color=blue>master node</font> 目录：  /etc/kubernetes/admin.conf   分发至出现该问题<font color=blue>worker node</font>的相同目录下
```
scp  /etc/kubernetes/admin.conf  user@IP_address:/etc/kubernetes/admin.conf
```
加入环境变量（注意要英文状态下的<font color=red>双引号</font>,不知道为啥markdown显示为中文状态下的双引号，自己注意替换）
```
echo “export KUBECONFIG=/etc/kubernetes/admin.conf” >> ~/.bash_profile
```
使环境变量配置生效
```
source ~/.bash_profile
```