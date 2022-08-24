FROM nginx
COPY default.conf /etc/nginx/conf.d/default.conf

#构建镜像
#docker build -t nginx .

#在终端里启动NGINX容器：
#docker run --name nginx -dp 8090:80 -v d:/karma/default.conf:/etc/nginx/conf.d/default.conf --link karma --volumes-from karma nginx
#-v d:/karma/default.conf:/etc/nginx/conf.d/default.conf 是把宿主机的NGINX配置文件复制到容器内
#--link karma 是把前一台容器的名称映射给这台容器，可供NGINX配置文件使用
#--volumes-from karma 是把前一台容器的共享目录挂载到这台容器的根目录

#如果NGINX镜像里已经有配置文件了
#docker run --name nginx -dp 80:80 --link testapp --volumes-from testapp nginx

#从容器里复制文件出来
#docker cp 62c51980c2d5:/etc/nginx/nginx.conf d:/karma/
#62c51980c2d5就是容器ID