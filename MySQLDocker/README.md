# MySQL 最新版容器安装

1.复制本目录到服务器

2.执行本目录下的Dockerfile以构建镜像，至本文件撰写时最新版本为8.0.30

`docker build -t mysql8.0.30 .`

3.启动容器，注意下方命令里ROOT密码可以更换

`docker run --name MySQL8.0.30 -dp 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 mysql8.0.30`
