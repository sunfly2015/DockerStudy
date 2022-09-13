FROM openjdk:20
COPY ./Projects /projects
WORKDIR /projects/mscode
#运行项目
CMD ["nohup","java", "-jar","mscode-gateway-3.0.2.jar","&"]
CMD ["nohup","java", "-jar","mscode-auth-3.0.2.jar","&"]
CMD ["nohup","java", "-jar","mscode-admin-service-3.0.2.jar","&"]
CMD ["nohup","java", "-jar","mscode-account-service-3.0.2.jar","&"]
#如果还需要运行其它模块按顺序加进来就好

#构建镜像
#docker build -t test_java_app .

#在终端里启动JAVA容器：
#docker run -it -dp 9001:9001 --name test_java_app test_java_app
#-i表示“交互式”的,-t表示生成一个终端