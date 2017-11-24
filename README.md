# LAMP Docker

This is an unofficial, open-source for LAMP based projects that run on Docker-Compose. 

    Apache 2.4
    Mysql 5.6
    Postgres 9.3
    PHP 5.4.16
    CENTOS 7

## Usage

You are up and running in three simple steps:

$ cd docker-lamp54

$ docker-compose up --build -d 

## Backup/Restore Mysql

* Backup

  sudo docker exec -i dockerlamp54_mysql_1 mysqldump -uroot -proot test > mysql/dumps/dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql

* Retore from a backup

  sudo docker exec -i dockerlamp54_mysql_1 mysql -u root -proot test < mysql/dumps/dump.sql


## Backup/Restore Postgres

* Backup

  sudo docker exec -i dockerlamp54_postgres_1 pg_dump -U postgres -d business > postgres/db/dumps/dump_`date +%d-%m-%Y"_"%H_%M_%S`.sql

* Restore from a backup 

  See the list of backups, you can run:

  sudo docker exec dockerlamp54_postgres_1 ls /db/dumps

* Restore

  sudo docker exec -i dockerlamp54_postgres_1 psql -U postgres -d business < postgres/db/dumps/dump.sql
