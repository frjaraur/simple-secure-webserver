FROM alpine:3.15
RUN addgroup -S nginx -g 10001 \
&& adduser -D -S -h /var/cache/nginx -s /sbin/nologin -G nginx -u 10001 nginx \
&& apk add --update --no-cache nginx \
&& rm -rf /var/cache/apk/* \
&& mkdir /html \
&& ln -sf /dev/stdout /var/log/nginx/access.log \
&& ln -sf /dev/stderr /var/log/nginx/error.log \
&& echo "default index">/html/index.html \
&& chown -R  nginx:nginx /html

COPY nginx.conf /etc/nginx/nginx.conf

COPY default.htpasswd /etc/nginx/auth/.htpasswd

USER 10001:10001

EXPOSE 1080

STOPSIGNAL SIGQUIT

CMD ["nginx","-g","pid /run/nginx.pid;daemon off;"]

