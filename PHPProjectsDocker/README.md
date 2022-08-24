# PHP 7.4 fpm 容器安装

1.复制本目录到服务器

2.执行本目录下的Dockerfile以构建镜像

`docker build -t testapp .`

3.启动容器

`docker run -dp 9000:9000 --name testapp testapp`
