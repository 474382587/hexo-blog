---
title: PHP functions
date: 2018-09-14 11:15:07
tags: [PHP]
---

## Random number
```php
<?php
int rand(void)
int rand ( int $min , int $max )
// Generate a random integer
?>
```
---
## Date
```php
<?php
string date ( string $format [, int $timestamp = time() ] )
?>
```
Format:
  - Y: 4 digits year
  - m: 2 digits month
  - d: 2 digits date
  - H: 2 digits hour
  - i: 2 digits minute
  - s: 2 digits second
  - w: 0~6, day of the week, 0 represents Sunday
---
## Time
`time()` --> Return current Unix timestamp 

---
`print_r()` --> Prints human-readable information about a variable
`print_r ( mixed $expression [, bool $return = FALSE ] )` --> If you would like to capture the output of print_r(), use the return parameter. When this parameter is set to TRUE, print_r() will return the information rather than print it.

---
`die('messge) exit('message')`　--> terminate progrom