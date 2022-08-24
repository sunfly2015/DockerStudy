FROM php:7.4-fpm
#安装PHP扩展
RUN docker-php-source extract \
    && docker-php-ext-install pdo_mysql \
	&& docker-php-source delete
COPY ./Projects /projects
WORKDIR /projects
#共享目录给其他容器
VOLUME [ "/projects" ]
RUN chmod -R 777 /projects/TestApp/runtime
RUN chmod -R 777 /projects/TestApp2/runtime

#CMD ["php", "./index.php"]

#构建镜像
#docker build -t testapp .

#在终端里启动PHP容器：
#docker run -dp 9000:9000 --name testapp testapp