---
title: docker创建镜像记录
author: kuroneko
tags:
  - docker
  - mysql
  - redis
  - netdata
categories:
  - 备忘录
  - linux
abbrlink: 42248
date: 2020-11-16 15:11:00
---
### docker
| 容器    | 脚本                                  | 备注 |
| :------: | :------------------------------------------------------------| :----:|
| mysql   | docker run --name mysql8 --restart=always -v /home/kuroneko/DockerData/mysql:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root -itd mysql:8.0.21 |      |
| redis   | docker run -v /home/kuroneko/DockerData/redis/conf/redis.conf:/usr/local/etc/redis/redis.conf -p 127.0.0.1:6379:6379 --restart=always -itd --name redis redis redis-server /usr/local/etc/redis/redis.conf |      |
| netdata |                                  如下                           |      |


```sh
docker run -d --name=netdata \
  -p 127.0.0.1:19999:19999 \
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