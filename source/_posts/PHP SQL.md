---
title: PHP SQL
date: 2018-10-01 10:59:07
tags: [PHP]
---

# PHP Manipulate MySQL

There are 3 ways to do this:

1. MySQL: Not permanent connection, not optimized, abandoned after PHP5.5
2. MySQLi: Permanent connection, only support MySQL
3. PDO: Similar as MySQLi, support most of the database

> use `phpinfo()` to see if your server support these

WAMP --> support all 3 by default  
Modify settings in php.ini

---

### MySQL

```php
  // 1. connect server/DB
  mysql_connect($server, $usertname, $password) or die('Error: DB connection failed.')
  ;

  // 2. select DB
  mysql_select_db($database_name) or die('Error: Database do not exist.');

  // 3. set charset encoding
  mysql_set_charset($charset);

  // 4. close connection
  mysql_close($link) // $link = mysql_connect(...)

  // die('Error: DB connection failed');

  // Execute SQL statement
  mysql_query($query); // Return Boolean value to indicate success/fail

  // ADD
  mysql_query("INSERT INTO users VALUES(NULL, 'NAME', 123)");

  // UPDATE
  mysql_query("UPDATE users SET money=25 where id=3");

  // DELETE
  mysql_query("DELETE FROM users where id=3");

  // DROP
  mysql_query("DROP TABLE test");


  // SELECT
  $result mysql_query("SELECT * FROM test");
  mysql_fetch_row($result); // return an index array
  mysql_fetch_assoc($result); // return an associate array
  mysql_fetch_array($result); // return a mixed array

  while($line = mysql_fetch_array($result)) {
    $data[] = $line;
  }
  var_dump($data);
```

---

### MySQLi

```php
  // connect database
  $connect = mysqli_connect('host', 'username', 'password', 'database');

  // perform sql query
  $result = mysqli_query($connect, $sql);

  // get results
  mysqli_fetch_all($result);
```

