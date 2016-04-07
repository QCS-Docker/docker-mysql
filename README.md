# docker-mysql

### 启动
```sh
docker run --name mysqld -e MYSQL_ROOT_PASSWORD=secret -d slsay/docker-mysql
```
mysqld: 容器名, secret: root用户密码

### 创建数据库
```sh
docker run -e MYSQL_DATABASE=mydb -e MYSQL_USER=userfoo -e MYSQL_PASSWORD=secret  -e MYSQL_ROOT_PASSWORD=verysecret -d slsay/docker-mysql
```
mydb: 数据库名，userfoo：用户名，secret:用户密码，verysecret: root用户密码

### 连接MySQL
```sh
docker run --link mysqld:mysql -it --rm slsay/docker-mysql bash
root@73304a3022fe:/# mysql -u root -p -h $MYSQL_PORT_3306_TCP_ADDR
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 4
Server version: 5.7.11 MySQL Community Server (GPL)

Copyright (c) 2000, 2016, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
```
