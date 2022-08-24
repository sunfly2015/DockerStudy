# Java + mscode 项目容器安装

## 安装 Nacos 容器

1.复制“nacos-docker”目录到服务器上
2.单机模式安装即可，在nacos-docker/example目录下执行：
`docker-compose -f example/standalone-derby.yaml up`
3.如果需要安装其他模式请参考：
[Nacos-Docker安装](https://nacos.io/zh-cn/docs/quick-start-docker.html "Nacos-Docker安装")

## 安装 Java + mscode 项目容器

1.执行本目录下的Dockerfile以构建镜像
`docker build -t test_java_app .`
2.启动容器
`docker run -it -dp 9001:9001 --name test_java_app test_java_app`