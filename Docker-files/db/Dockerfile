FROM mysql:8.4.0
LABEL "Project"="vprofile"
LABEL "Author"="alain"

ENV MYSQL_ROOT_PASSWORD="Gildas00@"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql 
