FROM mysql/mysql-server:latest

# Set environment variables
ENV MYSQL_ROOT_PASSWORD=53ecretP@ss
ENV MYSQL_DATABASE=csc468

# Copy the CSV file into the container
COPY cattle.csv /cattle.csv

# Start MySQL server and populate the database with the CSV data
RUN mysql -u root -p$MYSQL_ROOT_PASSWORD -e " \
    CREATE DATABASE csc468; \
    USE csc468; \
    CREATE TABLE cattle (id INT AUTO_INCREMENT PRIMARY KEY, color VARCHAR(255), horns VARCHAR(255)); \
    LOAD DATA INFILE '/cattle.csv' INTO TABLE cattle FIELDS TERMINATED BY ',' LINES TERMINATED BY '\n' IGNORE 1 ROWS;"     
