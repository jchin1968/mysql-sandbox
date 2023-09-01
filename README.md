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

## Resource Friendly Setup
Unless you're migrating from MySQL 5.7 to 8.0 or you're comparing the two versions, you do not need to have both servers running. Nor do you need to have phpMyAdmin running if you're comfortable using the MySQL command line or you have a DB editor already built into your IDE. 

So, to save on disk storage and memory usage, you can edit the docker-compose.yml file and simply comment out the unneccessary server configuration line. For example:

```
include:
# - compose-mysql-5.7.yml
 - compose-mysql-8.0.yml
# - compose-adminer.yml
``` 

# Usage
Once your docker container(s) is/are running you can use the following credentials to access the different services:
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
- phpMyAdmin
  - Host: http://localhost:8080


