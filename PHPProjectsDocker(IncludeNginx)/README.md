# Ubuntu + PHP7.4FPM + Nginx 容器

1.登录焰竹内网的容器镜像仓库

`docker login gs.yanzhuhealth.com:3001 -u 帐号 -p 密码`

2.启动容器

`docker run --name ubuntu-nginx-php7433（或按项目取名） -p 27011:80 -itd -v nginx配置文件在宿主机上的位置/nginx.conf:/etc/nginx/nginx.conf -v php项目在宿主机上的位置:/usr/share/nginx/html/ gs.yanzhuhealth.com:3001/yanzhuhealth/ubuntu-nginx-php7433:latest`
