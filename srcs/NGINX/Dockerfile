FROM alpine:3.19

RUN apk update && \
    apk add --no-cache nginx && \
    apk add openssl

COPY ./conf/nginx.conf /etc/nginx/nginx.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
