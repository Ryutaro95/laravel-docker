# DockerでPHP, MariaDB, apache環境を構築する

- docker image
  - php:8.1-apache
  - mariadb:10.3
  - phpmyadmin:latest
- PHP: 8.1
- DB: mariadb 10.3

```
.
├── www/
│    └── html/
│        └── index.php
├── compose.yml
└── docker/
    ├── app/
    │    ├── apache2/
    │    │    ├── sites-available/
    │    │    │   └── 000-default.conf
    │    │    └ apache2.conf
    │    ├── php.ini
    │    └── Dockerfile
    └── mysql/
         ├── initdb/
         ├── storage/
         ├── Dockerfile
         └── server.cnf
```
