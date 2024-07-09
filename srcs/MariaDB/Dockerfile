FROM alpine:3.19

RUN apk update && \
    apk add --no-cache mariadb mariadb-client

RUN mkdir -p /run/mysqld && chown -R mysql:mysql /run/mysqld && \
    mkdir -p /var/lib/mysql && chown -R mysql:mysql /var/lib/mysql && \
    mkdir -p /var/log/mysql && chown -R mysql:mysql /var/log/mysql

COPY ./conf/my.cnf /etc/mysql/my.cnf

EXPOSE 3306

RUN mysql_install_db --user=mysql --ldata=/var/lib/mysql

CMD ["mysqld", "--user=mysql"]
