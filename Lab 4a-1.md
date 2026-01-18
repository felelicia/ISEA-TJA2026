## Additional Server Implementation 
## MARIADB / MYSQL DATABASE SERVER

Type: Relational Database Management System 

Purpose: Backend storage for web apps like WordPress, Moodle, ERPNext, etc.

## Installation

sudo apt update

sudo apt install mariadb-server mariadb-client -y

or

sudo apt install mysql-server mysql-client -y

Secure installation

sudo mysql_secure_installation

Basic DB operations

sudo mysql

CREATE DATABASE sampledb;

CREATE USER 'appuser'@'localhost' IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON sampledb.* TO 'appuser'@'localhost';

FLUSH PRIVILEGES;

EXIT;

⚙️ Performance

· Tune /etc/mysql/mariadb.conf.d/50-server.cnf

· Use innodb_buffer_pool_size ~70% of RAM for large DB

· Regular backups via mysqldump
