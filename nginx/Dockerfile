FROM alpine
LABEL maintainer="Name <foo@bar.com>"

RUN addgroup -g 6000 nginx \
     && adduser -SH \
    -s /sbin/nologin \
    -u 6000 \
    -h /var/cache/nginx \
    -G nginx nginx 
RUN apk update && apk upgrade
RUN apk add nginx \ 
bash
RUN ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log

COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 80

STOPSIGNAL SIGTERM

CMD ["nginx", "-g", "daemon off;"] 
