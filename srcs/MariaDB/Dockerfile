FROM debian:bullseye

RUN apt-get update
RUN apt install -y mariadb-server
RUN mkdir -p /run/mysqld && chown -R mysql:mysql /run/mysqld

COPY ./conf/50-server.cnf etc/mysql/mariadb.conf.d/

COPY mariadb-setup.sh /
RUN chmod +x /mariadb-setup.sh

ENTRYPOINT [ "/mariadb-setup.sh" ]
