FROM debian:buster

RUN apt update
RUN apt install -y mariadb-server procps

EXPOSE 3306

COPY ./tools/mariadb-setup.sh /tmp/mariadb-setup.sh
RUN chmod +x /tmp/mariadb-setup.sh

COPY ./conf/50-server.cnf etc/mysql/mariadb.conf.d/50-server.cnf

ENTRYPOINT [ "sh", "/tmp/mariadb-setup.sh" ]

CMD ["mysqld_safe"]
