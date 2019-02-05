mysql-ctl start

mysql -u $C9_USER -p   (no password required)

show databases;

mysql> show databases;

output:
+--------------------+
| Database           |
+--------------------+
| information_schema |
| c9                 |
| mysql              |
| performance_schema |
| phpmyadmin         |
+--------------------+
5 rows in set (0.00 sec)

download Chinook_MySQL to cloud9:           CHINOOK DATABASE

wget https://raw.githubusercontent.com/lerocha/chinook-database/master/ChinookDatabase/DataSources/Chinook_MySql_AutoIncrementPKs.sql

to run the script and create populated database:
mysql -u $C9_USER -p < Chinook_MySql_AutoIncrementPKs.sql       (no password)

mysql -u $C9_USER -p                (no password)

show databases;                 (will display the databases)

use Chinook;                (tell server to use Chinook)
show tables;

desc Genre;                 (use desc command to view properties of the table)

tee file.txt                (log all mysql command line activity to file.txt)
notee                       (stop logging)


create test.sql file containing:
select count(*) from Track;
select count(*) from Artist; /* counts number of rows in artist and album tables*/

type:
source test.sql                         (to run the test.sql script) ..
