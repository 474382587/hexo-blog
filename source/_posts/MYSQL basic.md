---
title: MySQL Basics
date: 2018-10-02 22:40:34
tags: [MySQL]
---

# MySQL Basics

- Config file --> my.cnf
- Login --> 1. command line `mysql -uroot -p` then enter password 2. `mysql -uroot -ppassword`
- Logout --> 1. `exit`
  2. `quit`
  3. \q
- Login `mysql -h"host_address" -uroot -p -P3306` --> add host and port number
- login and open a DB `mysql -uroot -p -D db_name`

Common SQL

- `SELECT USER();` --> Login User Info
- `SELECT VERSION();` -->MYSQL Version
- `SELECT NOW();` --> Get current date time
- `SELECT DATABASE();` --> Get current Database

## Create database

1. `CREATE DATABASE db_name;`
2. `CREATE SCHEMA db_name;`
3. `CREATE DATABASE IF NOT EXISTS db_name;`
4. `CREATE DATABASE IF NOT EXISTS db_name DEFAULT CHARACTER SET 'UTF8';`
---

## Show all databases

`SHOW DATABASES;`    
`SHOW SCHEMAS;`

---

## Common 
`SHOW WARNINGS`    
`SHOW CREATE DATABSE db_name;`    
Modify DATABASE `ALTER DATABSE db_name DEFAULT CHARACTER SET=charset;`    
Open sepcific db: `USE db_name;`    
Select current db --> `SELECT DATABASE();`
Delete a db --> `DROP DATABSE db_name;` --> `DROP DATABSE db_name IF EXISTS;`

---

## TABLES
> Includes `ROW` and `COLUMN`    
> At least has one `COLUMN`, `ROW` can be 0    
> Has to be unique

Type:   
- Number
  - Integer
    - TINYINT 
    - SMALLINT
    - MEDIUMINT
    - INT
    - BIGINT
    - BOOL,BOOLEAN
  - Float
    - FLOAT
    - DOUBLE
    - DECIMAL
- String
  - CHAR
  - VARCHAR
  - TINYTEXT
  - TEXT
  - MEDIUMTEXT
  - LONGTEXT
  - ENUM('value1', 'value2', ...)
  - SET('value1', 'value2', ...)
- Date 
  - TIME
  - DATE
  - DATETIME
  - TIMESTAMP
  - YEAR

Create table:
- 
  ```sql
  CREATE TABLE IF NOT EXISTS table_name(
    name type conditions
    username 
  )ENGINE="" CHARSET="";
  ```

  ---
  ```sql
    USE mydatabase; 
    CREATE TABLE IF NOT EXIST user(
      id INT,
      username, VARCHAR(20),
      password CHAR(32),
      email VARCHAR(50),
      card CHAR(18),
      tel CHAR(11),
      salary FLOAT(8,2),
      married TINYINT(1),
      gender ENUM('Male', 'Female', 'Unknow'),
      addr VARCHAR(100)
    )ENGINE=INNODB CHARSET=UTF8;

  ```
  ## Look current tables
  - `SHOW TABLES;`    
  - `SHOW CREATE TABLE table_name;` --> show create table details - `DESC table_name;` ---> show structure of the table
  - `DESCRIBE table_name;` ---> show structure of the table
  - `SHOW COLUMNS FROM table_name;` ---> show structure of the table
 
  ## delete table
  - `DROP TABLE IF EXISTS table_name;`
 
 ```sql
 SHOW TABLES;
 SHOW TABLES FROM users;
 DESC users;
 DESCRIBE users;
 SHOW COLUMNS FROM users;
 DROP TABLE IF EXISTS users;
 ```

## constraints
- unsigned -> no negative, from 0
- zerofill -> use 0 to fill unfilled digits
- NOT NULL -> cannot be empty
- DEFAUL -> default value
- PRIMARY KEY -> unique, one table each
- UNIQUE KEY -> unique(except null), can have multiple
- AUTO_INCREMENT -> auto increment, can only apply to number columns
- FOREIGN KEY -> outside constraints
---