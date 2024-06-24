FROM mysql:8.0.33
LABEL "Project"="vprofile"
LABEL "Author"="Imran"

ENV MYSQL_ROOT_PASSWORD="123456789"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
