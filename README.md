This project creates a MySQL sandbox using Docker. It includes both MySQL 5.7 and 8.0 servers, phpMyAdmin client and Percona's pt-query-digest tool.

# Installation
## Minimum Requirements
- Docker Engine 23.0 
- Docker Compose 2.20

## Quick Start
The following steps create a sandbox with both MySQL servers and phpMyAdmin in separate docker containers.

```
git clone https://github.com/jchin1968/mysql-sandbox
cd mysql-sandbox
docker-compose up -d
```

## Resource Friendlier Setup
Unless you're migrating from MySQL 5.7 to 8.0 or you're comparing the two versions, you do not need to have both servers running. Nor do you need to have phpMyAdmin running if you're comfortable using the MySQL command line or you have a DB editor already built into your IDE. 

So, to save on disk storage and memory usage, you can edit the docker-compose.yml file and simply comment out the unneccessary server configuration line. For example:

```
include:
# - compose-mysql-5.7.yml
 - compose-mysql-8.0.yml
# - compose-adminer.yml
``` 

## Custom MySQL Configurations
Create a MySQL cnf file and place in either ./config/5.7 or ./config/8.0 folders

# Usage
Once your docker container(s) is/are running you can connect to the database server using a number of ways.

## Command Line
The MySQL server includes a command line client which you can access using the docker command ```ddocker exec -it [CONTAINER_NAME] mysql -uroot -ptest [DB_NAME]``` where:
- CONTAINER_NAME is mysql57 or mysql80
- and DB_NAME is an optional value

Example:
```
docker exec -it mysql80 mysql -uroot -ptest demo
```

## phpMyAdmin
MySQL Sandbox includes phpMyAdmin, a web-based database client. To use phpMyAdmin, go to http://localhost:8080 on your host computer browser and use the following credentials depending on the MySQL version:

- MySQL 5.7
  - Host: mysql57.docker 
  - Port: 3306
  - User: root
  - Password: test
- MySQL 8.0
  - Host: mysql80.docker
  - Port: 3306
  - User: root
  - Password: test

## Installed Host Database Client/Editor
If you have a database client or editor (i.e. DBeaver, Toad, JetBrain IDE) already installed on your host computer, use the following credentials:

- MySQL 5.7
  - Host: localhost
  - Port: 30657
  - User: root
  - Password: test
- MySQL 8.0
  - Host: localhost
  - Port: 30680
  - User: root
  - Password: test


