---
title: PHP Bubble Sort
date: 2018-09-17 17:15:07
tags: [PHP, Algorithm]
---
```php
<?php
// [4, 9, 8, 6, 7, 3, 2, 1]

$arr = [4, 9, 8, 6, 7, 3, 2, 1];

function bullingSort($arr) {
  $checkPoint = 0;
  while(true) {
    $swapCount = check($arr, $checkPoint);
    $checkPoint++;
    if ($swapCount <= 0) {
      return $arr;
    }
  }
}

function check(&$arr, $checkPoint) {
  $swapCount = 0;
  for ($i = count($arr) - 1; $i > $checkPoint; $i--) {
    if ($arr[$i] < $arr[$i - 1]) {
      swap($arr, $i);
      $swapCount++;
    }
  }
  return $swapCount;
}

function swap(&$arr, $i) {
  $tmp = $arr[$i];
  $arr[$i] = $arr[$i - 1];
  $arr[$i - 1] = $tmp;
}

print_r( bullingSort($arr) );


```

