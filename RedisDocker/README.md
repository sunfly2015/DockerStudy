# Redis 5.0.14 容器安装

1.复制本目录到服务器

2.执行本目录下的Dockerfile以构建镜像

`docker build -t redis:5.0.14 .`

3.启动容器，注意“–appendonly yes”是开启持久化，“--requirepass 123456”设置密码为123456

`docker run -p 6379:6379 --name redis_5_0_14 -d redis:5.0.14 --appendonly yes  --requirepass 123456`
