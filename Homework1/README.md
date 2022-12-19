## Домашнее задание #1 Docker

1. Создаем Dockerfile для сборки образа следующего содержания:  
	```
	user@linux1:~/linux/homework-09$ cat Dockerfile
	
	FROM alpine:latest
	LABEL maintainer="Aleksey Sboev <sboevav@mail.ru>"

	RUN apk update \
	    && apk upgrade \
	    && apk add nginx \
	    && mkdir -p /run/nginx

	COPY nginx.conf /etc/nginx/conf.d/default.conf 
	COPY index.html /usr/share/nginx/html/index.html

	EXPOSE 7777

	CMD ["nginx", "-g", "daemon off;"]
	```
2. Создаем файл nginx.conf с дополнительной конфигурацией nginx следующего содержания:  
	```
	user@linux1:~/linux/homework-09$ cat nginx.conf 

	server {
	  listen       7777;
	  server_name  localhost;
	  root   /usr/share/nginx/html;
	  index  index.html index.htm;

	  location / {
	    try_files $uri /index.html;
	  }
	}
	```
3. Берем дефолтную страницу nginx, которую будем выдавать из нашего контейнера и слегка изменяем ее ширину и заголовок на следующее содержание:  
	```
	<!DOCTTYPE html>
    <html>
        <head>
            <title> Hello example </title>
        </head>
        <body>
            <p> Hello World! </p>
        </body>
    </html>
	```
4. Установим необходимый инструментарий  
	```
	sudo apt  install docker.io
	```
5. Приступаем к сборке образа nginx:alpine 	```
	
	sudo docker build -t nginx:alpine .

	
6. Проверяем, что получили после сборки  
	```
	sudo docker images -a
	
	
7. Запускаем контейнер с указанием проброса 7777-го порта и проверяем, что контейнер запущен  
	```
	sudo docker run -d -p 7777:80 nginx:alpine
	
	sudo docker ps
