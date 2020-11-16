title: 部署k8s笔记（一）
author: kuroneko
tags:
  - 'k8s '
  - kubernetes
categories: linux
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
将<font color=blue>master node</font> 目录：  /etc/kubernetes/admin.conf   分发至出现该问题的相同目录下
```
scp  /etc/kubernetes/admin.conf  user@IP_address:/etc/kubernetes/admin.conf
```