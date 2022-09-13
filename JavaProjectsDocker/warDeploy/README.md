# Java + war 项目容器安装

## 以一个名为eval的项目为例，注意：本项目tomcat版本是7.0.109

1.复制“eval”目录到服务器上

2.本项目依赖容器内的tomcat才能运行

3.根据实际情况修改“eval”目录下的docker-compose.yml文件中第9行和第10行

```
- /mnt/docker/eval/tomcatconf:/usr/local/tomcat/conf
- /mnt/docker/eval/www:/usr/local/tomcat/webapps
```

4.第9行表示宿主机“/mnt/docker/eval/tomcatconf”目录，映射到容器内tomcat配置文件目录，可以根据实际情况调整本目录下的server.xml文件，然后复制到宿主机映射的tomcat配置目录

5.第10行表示宿主机“/mnt/docker/eval/www”目录，映射到容器内tomcat默认的应用根目录

6.复制修改后的docker-compose.yml文件到服务器

7.执行docker-compose以构建镜像并部署

`docker-compose up -d`

## 延伸阅读

1.如果还需要在同一个tomcat下增加其它项目，可以把其它项目的*.war文件复制到宿主机“/mnt/docker/eval/www”目录

2.然后自行按照实际情况修改宿主机“/mnt/docker/eval/tomcatconf”目录下的server.xml文件，针对这些增加的项目改写tomcat配置文件

3.然后重启tomcat即可
`docker restart 容器ID`