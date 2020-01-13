# SQL

mysql> CREATE DATABASE nhl_player_data;
Query OK, 1 row affected (0.01 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| nhl_player_data    |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

mysql> DROP DATABASE sys;
Query OK, 101 rows affected (0.13 sec)

mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| nhl_player_data    |
| performance_schema |
+--------------------+
4 rows in set (0.00 sec)

mysql> USE nhl_player_data;
Database changed

mysql> SELECT DATABASE ();
+-----------------+
| DATABASE ()     |
+-----------------+
| nhl_player_data |
+-----------------+
1 row in set (0.00 sec)

mysql> CREATE TABLE nhl_stats
    -> (
    -> nhl_id INT NOT NULL AUTO_INCREMENT,
    -> Name VARCHAR(100),
    -> Country VARCHAR(100),
    -> Points INT,
    -> PRIMARY KEY (NHL_ID)
    -> );
Query OK, 0 rows affected (0.04 sec)

mysql> DESC nhl_stats;
+---------+--------------+------+-----+---------+----------------+
| Field   | Type         | Null | Key | Default | Extra          |
+---------+--------------+------+-----+---------+----------------+
| nhl_id  | int(11)      | NO   | PRI | NULL    | auto_increment |
| Name    | varchar(100) | YES  |     | NULL    |                |
| Country | varchar(100) | YES  |     | NULL    |                |
| Points  | int(11)      | YES  |     | NULL    |                |
+---------+--------------+------+-----+---------+----------------+
4 rows in set (0.00 sec)

mysql> INSERT INTO nhl_stats(name, country, points) VALUES ('Conor_Mcdavid', 'Canada',116);
Query OK, 1 row affected (0.01 sec)

mysql> SELECT * FROM nhl_stats;
+--------+---------------+---------+--------+
| nhl_id | Name          | Country | Points |
+--------+---------------+---------+--------+
|      1 | Conor_Mcdavid | Canada  |    116 |
+--------+---------------+---------+--------+
1 row in set (0.00 sec)

mysql> INSERT INTO nhl_stats(name, country, points) VALUES ('Brad_Marchand','Canada',100);
Query OK, 1 row affected (0.00 sec)

mysql> SELECT * FROM nhl_stats;
+--------+---------------+---------+--------+
| nhl_id | Name          | Country | Points |
+--------+---------------+---------+--------+
|      1 | Conor_Mcdavid | Canada  |    116 |
|      2 | Brad_Marchand | Canada  |    100 |
+--------+---------------+---------+--------+
2 rows in set (0.00 sec)

mysql> INSERT INTO nhl_stats
    -> (name,country,points)
    -> Values
    -> ('Aleksander_Barkov','Finland', 96)
    -> ,('Nikita_Kucherov', 'Russia', 128)
    -> ,('Nathan_Mackinnon', 'Canada', 99)
    -> ;
Query OK, 3 rows affected (0.00 sec)
Records: 3  Duplicates: 0  Warnings: 0

mysql> SELECT * FROM nhl_stats;
+--------+-------------------+---------+--------+
| nhl_id | Name              | Country | Points |
+--------+-------------------+---------+--------+
|      1 | Conor_Mcdavid     | Canada  |    116 |
|      2 | Brad_Marchand     | Canada  |    100 |
|      3 | Aleksander_Barkov | Finland |     96 |
|      4 | Nikita_Kucherov   | Russia  |    128 |
|      5 | Nathan_Mackinnon  | Canada  |     99 |
+--------+-------------------+---------+--------+
5 rows in set (0.00 sec)

