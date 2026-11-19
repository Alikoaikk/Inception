FROM alpine:3.23

RUN apk add --no-cache mariadb mariadb-client \ 
        mkdir -p /run/mysql                   \
        chown -R mysql:mysql /run/mysql /var/lib/mysql

COPY conf/mariadb-server.cnf /etc/my.cnf.d/mariadb-server.cnf 

COPY tools/setup.sh /usr/local/bin/setup.sh 
RUN chmod +x /usr/local/bin/setup.sh

EXPOSE 3306

ENTRYPOINT ["/usr/local/bin/setup.sh"]
