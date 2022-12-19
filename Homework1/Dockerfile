FROM alpine:latest

RUN apk update \
    && apk upgrade \
    && apk add nginx \
    && mkdir -p /run/nginx

COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY . /usr/share/nginx/html

EXPOSE 7777

CMD ["nginx", "-g", "daemon off;"]









