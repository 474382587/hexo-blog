---
title: PHP Array Traversal
date: 2018-09-21 22:57:34
tags: [PHP, Array]
---

## Traversal

1. foreach
2. array pointer
3. `each()` and `list()`
---
```php
// One Demension
// foreach
/*
  foreach($array_name as $val) {
    //
  }

  foreach($array_name as $key=>$val) {

  }
*/
  $arr = [
    '5'=>'11',
    '55'=>'a',
    '555'=>'2'
  ];
  foreach($arr as $item) {
    echo $item;
  }

  foreach($arr as $key=>$item) {
    echo $key,'=>',$item;
  }

// 2D Array
$users = [
  ['age'=>15, 'id'=>1233],
  ['age'=>22, 'id'=>1223],
  ['age'=>12, 'id'=>1243],
];

foreach($users as $user) {
  echo $user['age'];
}
```

---
## Array Pointer
`key($array)` => return current key name of the pointer
`current($array)` => return current value of the pointer
`next($array)` => return next value of the pointer, return false if no next
`prev($array)` => return previous value of the pointer, return false if no previous
`end($array)` => last value of the pointer
`reset($array)`
```php
```