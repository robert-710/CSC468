FROM mysql/mysql-server:latest

# Set environment variables
ENV MYSQL_ROOT_PASSWORD=$3ecretP@ss
ENV MYSQL_DATABASE=csc468

# Copy the CSV file into the container
COPY cattle.csv /cattle.csv

# Start MySQL server and populate the database with the CSV data
RUN /entrypoint.sh mysqld & sleep 30s && \
    mysql -u root -p$MYSQL_ROOT_PASSWORD -e "CREATE TABLE csc468.cattle (id INT AUTO_INCREMENT PRIMARY KEY, color VARCHAR(255), horns VARCHAR(255));" && \
    mysqlimport -u root -p$MYSQL_ROOT_PASSWORD --local csc468 /cattle.csv
