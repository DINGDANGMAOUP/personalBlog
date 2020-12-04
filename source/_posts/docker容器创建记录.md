title: docker容器创建记录
author: kuroneko
abbrlink: 37080
tags:
  - docker
  - mysql
  - redis
  - netdata
categories:
  - docker
  - linux
date: 2020-12-04 10:56:00
---
### 在搭建环境过程中用到的一些容器
+ msyql

```
docker run –name mysql8 –restart=always -v /home/kuroneko/DockerData/mysql:/var/lib/mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=root -itd mysql:latest

```
+ redis

```
docker run -itd --restart=always  -v /home/kuroneko/DockerData/redis/conf/redis.conf:/usr/local/etc/redis/redis.conf  -p 6379:6379 --name redis redis redis-server /usr/local/etc/redis/redis.conf
```
+ netdata

```
docker run -itd --name=netdata \
  -p 19999:19999 \
  -v netdatalib:/var/lib/netdata \
  -v netdatacache:/var/cache/netdata \
  -v /etc/passwd:/host/etc/passwd:ro \
  -v /etc/group:/host/etc/group:ro \
  -v /proc:/host/proc:ro \
  -v /sys:/host/sys:ro \
  -v /etc/os-release:/host/etc/os-release:ro \
  --restart unless-stopped \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
```