# Postgres

# Back up one table

* pg_dump --table crm_prospect  -U nokia goal -f crm_prospect.sql
* psql -f crm_prospect.sql goal

# Master Slave configuration

* https://www.digitalocean.com/community/tutorials/how-to-set-up-master-slave-replication-on-postgresql-on-an-ubuntu-12-04-vps
* http://www.rassoc.com/gregr/weblog/2013/02/16/zero-to-postgresql-streaming-replication-in-10-mins/

# pg_data change

For this is better to create a different table_space on a directory with more space 
and then create the db in that tablespace. 
* create tablespace temp_tbs location '/ephemeral/tpm/';
*  create database claro_delivery TABLESPACE custom_tablespace;


* http://www.whiteboardcoder.com/2012/04/change-postgres-datadirectory-folder.html


# Failling tmp for hash join on database. 

*http://stackoverflow.com/questions/29602409/could-not-write-to-hash-join-temporary-file-no-space-left-on-device

# general use on psql 

* createdb nameofdb
* createuser --interactive --pwprompt --no-superuser --no-createrole --no-createdb nameofuser
* psql --dbname=postgres://nameofuser:passwd@localhost/nameofdb   (test connection)
* restore: pg_restore --dbname=postgres://zinalat:zinalat@localhost/zinalat  --no-acl --no-owner -c /tmp/2017.07.27_zinalat_database.sql
* dump: pg_dump --dbname=postgres://ipmservice:ipmservice@localhost/ipmservice --no-acl  --no-owner -Fc -f /tmp/ipmservice_12.07.2017.sql

