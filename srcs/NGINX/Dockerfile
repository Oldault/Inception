FROM alpine:3.19

RUN apk update && \
    apk add --no-cache nginx openssl tini
    
EXPOSE 80 443

RUN mkdir -p /etc/nginx && \
    mkdir -p /var/www && \
    mkdir -p /etc/ssl/certs && \
    mkdir -p /etc/ssl/private
    
COPY ./conf/nginx.conf /etc/nginx/nginx.conf
COPY ./tools/start.sh /var/www/start.sh

RUN chmod +x /var/www/start.sh

ENTRYPOINT ["/sbin/tini", "--"]

CMD ["sh", "/var/www/start.sh"]
