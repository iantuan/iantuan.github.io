---
layout     : post
title      : "Pomelo Study"
subtitle   : "deploy pomelo"
date       : 2018-02-27 10:39:51 +0800
author     : "iantuan"
tags       : Game-Server
comments   : true
signature  : true
---

### Create Docker network

```
$ docker network create pomelo
```

### Create Database Docker Container

```
$ docker run --name pomelomysql -e MYSQL_ROOT_PASSWORD=12345 -p 3306:3306 -v $PWD:/root/loardofpomelo --network pomelo -d mysql
```
### Create Pomelo docker

```
$ docker run -ti --name mypomelo -v $PWD:/rrot/node/loardofpomelo -p 3001:3001 -p 3014:3014 -p 30101:3010 -p 3011:3011 --network pomelo node:4 bash
```
### Setup Pomelo Environment

```
$ cd /root/node/loardofpomelo
 
$ sh nom-install.sh
 
$ npm install -g component
 
$ cd web-server
$ sh bin/component.sh
 
$ npm install pomelo -g
$ apt-get update
$ apt-get install sysstat
```

### Start Game Server
```
$ cd game-server
$ pomelo start -e development
```

### Start Web Server

```
$ cd web-server
$ node app
```



