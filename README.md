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

That's it! You can use the following credentials to access the different servers:
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

