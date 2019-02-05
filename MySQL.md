mysql-ctl start

mysql -u $C9_USER -p   (no password required)

show databases;

mysql> show databases;

github for chinook:
https://github.com/lerocha/chinook-database/tree/master/ChinookDatabase/DataSources

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

select * from Album  limit 5;           (limits query results to 5)

select Title, Name from Album                               (shows artist name and album)
join Artist on Album.ArtistId = Artist.ArtistId         (join artist and album tables using artistId to match them)
limit 5;


INSERTING RECORDS:

insert into Genre (Name) values('Trad');    (at mysql or script file. the command here creates a new genre)

SELECT LAST_INSERT_ID();                     (find ID of last insert)
select * from Genre where GenreId = 26;     (querying that ID returns the genre we created)


UPDATING RECORDS:       (can be entered at MySQL prompt or via script file)

update Genre set Name ='Traditional' where Name = 'Trad';       (changes Genre from Trad to Traditional)

select * from Genre;                      (query Genre table shows this change)


DELETING RECORDS:       (at MySQL or script file)

delete from Genre where Name = 'Traditional';       (delete Traditional file)

select * from Genre where Name = 'Traditional';     (won't find it as we deleted it...empty set)



















