# 禅道容器安装

## 安装 zentao + MySQL 容器

1.复制“ZentaoDocker”目录到服务器上

2.在目录下执行：

`docker-compose up -d`

3.然后在浏览器里打开如下网址开始安装禅道系统（容器内已经包含了MySQL数据库）

`http://IP:9001/`

4.如果需要安装其他模式请参考：

[zentao-Docker安装](https://hub.docker.com/r/easysoft/zentao "zentao-Docker安装")

## 关于docker-compose的说明

1.docker-compose.yml文件不能使用制表符，请使用空格

2.关于端口

`ports:
    - 9001:80`

表示物理机端口9001指向容器端口80

3.关于持久化

(```)
volumes:
   - /mnt/docker/linshanzentao/zentao:/www/zentaopms
   - /mnt/docker/linshanzentao/mysqldata:/var/lib/mysql
(```)

物理机的“/mnt/docker/linshanzentao/zentao”目录，映射到容器内“/www/zentaopms”，这是禅道项目目录

物理机的“/mnt/docker/linshanzentao/mysqldata”目录，映射到容器内“/var/lib/mysql”，这是禅道数据库目录

以上两个目录可以复制出来做备份或修改

4.容器启动启动

`restart: always`

表示容器自动启动

5.容器内MySQL数据库密码

`environment:
   - MYSQL_ROOT_PASSWORD=lszt123`

表示数据库密码设置为“lszt123” 