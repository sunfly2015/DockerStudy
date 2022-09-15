# Java + mscode 项目容器安装

## 安装 Nacos 容器

1.复制“nacos-docker”目录到服务器上

2.单机模式安装即可，在nacos-docker/example目录下执行：

`docker-compose -f example/standalone-derby.yaml up`

3.如果需要安装其他模式请参考：

[Nacos-Docker安装](https://nacos.io/zh-cn/docs/quick-start-docker.html "Nacos-Docker安装")

## 安装 Java + mscode 项目容器

1.根据实际情况修改本目录下的docker-compose.yml文件中第9行

```
- /mnt/docker/jartest/mscode:/projects
```

2.第9行表示宿主机“/mnt/docker/jartest/mscode”目录，映射到容器内存放项目的目录“/projects”

3.复制docker-compose.yml文件到服务器

4.执行docker-compose以构建镜像并部署

`docker-compose up -d`

## 直接在容器中编译jar项目

1.复制项目代码到宿主机“/mnt/docker/jartest/mscode”目录

2.连接容器终端

```
docker exec -it 容器ID bash
```

3.进入容器内“/projects”目录（假设这个目录就是项目根目录），运行编译命令

```
mvn compile
或者
mvn clean compile
```

4.然后打包成jar

```
mvn package
```

5.运行jar

```
java -jar jar包文件名 &
或者
nohup java -jar jar包文件名 &
```

## 关于容器启动后立刻停止的说明

1.容器运行必须有一个前台进程， 如果没有前台进程执行，容器认为空闲，就会自行退出

2.容器运行的命令如果不是那些一直挂起的命令（ 运行top，tail、循环等），就是会自动退出

3.在“docker-compose.yml”文件中第11~13行可以解决这个问题

```
command: ["/bin/bash"]
stdin_open: true
tty: true
```

4.如果是手动启动容器可以使用如下格式解决这个问题

```
docker run -dit --name 容器名称 /bin/bash sunfly2009/centos7_java1_8:7.9.2009
```
