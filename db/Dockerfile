FROM mysql

# Environment variables
ENV MYSQL_ROOT_PASSWORD password

# Create Database
RUN	mkdir /usr/sql
RUN	chmod 644 /usr/sql

ADD ./dump.sql /usr/sql/dump.sql

RUN /etc/init.d/mysql start && \
        mysql -uroot -p${MYSQL_ROOT_PASSWORD} -e "CREATE DATABASE av" && \
    	mysql -u root -p${MYSQL_ROOT_PASSWORD} -D av < /usr/sql/dump.sql