
FROM mysql/mysql-server:latest

# Set environment variables
ENV MYSQL_ROOT_PASSWORD=53cretP@ss
ENV MYSQL_DATABASE=csc468

COPY cattle.csv /var/lib/mysql-files/

COPY init_db.sql /docker-entrypoint-initdb.d/
