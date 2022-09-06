# Nginx 最新版容器安装

## 手动安装

1.按照实际情况修改本目录下的default.conf，本配置文件是以名叫“testapp”的一个PHP应用为示例

2.复制本目录到服务器

3.执行本目录下的Dockerfile以构建镜像

`docker build -t nginx .`

4.启动容器，注意下方命令里“--link testapp”是把另一个叫“testapp”的容器连接到本容器，“--volumes-from testapp”是把“testapp”容器的共享目录挂载到这台容器的根目录

`docker run --name nginx -dp 80:80 --link testapp --volumes-from testapp nginx`

##自动安装

1.根据实际情况修改本目录下的docker-compose.yml文件中第9行和第10行

```
- /mnt/docker/nginx/config:/etc/nginx/conf.d
- /mnt/docker/nginx/www/html:/usr/share/nginx/html
```

2.第9行表示宿主机“/mnt/docker/nginx/config”目录，映射到容器内nginx配置文件目录，可以根据实际情况调整本目录下的default.conf文件，然后复制到宿主机映射的nginx配置目录

3.第10行表示宿主机“/mnt/docker/nginx/www/html”目录，映射到容器内nginx默认的网站根目录

2.复制docker-compose.yml文件到服务器

3.执行docker-compose以构建镜像并部署

`docker-compose up -d`