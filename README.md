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
docker run -it slsay/docker-mysql bash
```
