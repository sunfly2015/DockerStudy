# Nginx 最新版容器安装

1.按照实际情况修改本目录下的default.conf，本配置文件是以名叫“testapp”的一个PHP应用为示例
2.复制本目录到服务器
3.执行本目录下的Dockerfile以构建镜像
`docker build -t nginx .`
4.启动容器，注意下方命令里“--link testapp”是把另一个叫“testapp”的容器连接到本容器，“--volumes-from testapp”是把“testapp”容器的共享目录挂载到这台容器的根目录
`docker run --name nginx -dp 80:80 --link testapp --volumes-from testapp nginx`