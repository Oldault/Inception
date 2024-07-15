FROM debian:bullseye

RUN apt update && \
    apt upgrade -y && \
    apt install -y nginx openssl

RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
    -keyout /etc/ssl/private/svolodin.key \
    -out /etc/ssl/certs/svolodin.crt \
    -subj "/C=FR/ST=Paris/L=Paris/O=42/CN=svolodin.42.fr"

RUN openssl dhparam -out /etc/nginx/dhparam.pem 2048
COPY ./conf/self-signed.conf /etc/nginx/snippets/

COPY ./conf/default /etc/nginx/sites-available/
COPY ./conf/adminer.conf /etc/nginx/sites-available/

ENTRYPOINT ["nginx", "-g", "daemon off;"]
