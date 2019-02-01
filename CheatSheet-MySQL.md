# MySQL CheatSheet
___
To output the list of databases:
```sql
SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
```
To create a new database:
```sql
CREATE DATABASE databasename;
```
To put one of the databases to use:
```sql
USE databasename;
```
To see which database is currently in use:
```sql
SELECT DATABASE();
+--------------+
| DATABASE()   |
+--------------+
| databasename |
+--------------+
```
To create a table named "books" with some fields that can't be `NULL`:
```sql
CREATE TABLE books (  
    -> title VARCHAR(50) NOT NULL, 
    -> author VARCHAR(50) NOT NULL, 
    -> book_id INT UNSIGNED NOT NULL AUTO_INCREMENT PRIMARY KEY);
```
To see what tables are in the database that's being used:
```sql
SHOW TABLES;
+------------------------+
| Tables_in_databasename |
+------------------------+
| books                  |
+------------------------+
```

To see the schema of a table names `books` of a database called `databasename`:
```sql
DESCRIBE databasename.books;
+---------+------------------+------+-----+---------+----------------+
| Field   | Type             | Null | Key | Default | Extra          | 
+---------+------------------+------+-----+---------+----------------+
| title   | varchar(50)      | NO   |     | NULL    |                |
| author  | varchar(50)      | NO   |     | NULL    |                |
| book_id | int(10) unsigned | NO   | PRI | NULL    | auto_increment |
+---------+------------------+------+-----+---------+----------------+
```

To add a new field ('language') to an existing table, after a field ('author'):
```sql
ALTER TABLE books ADD language VARCHAR(50) AFTER author;
```



















