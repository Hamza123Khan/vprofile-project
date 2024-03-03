FROM mysql:8.0.32
LABEL "project"="vprofile"
LABEL "Auther"="Hamza Gul Khan"

ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql -entrypoint-initdb.d/db_backup.sql
