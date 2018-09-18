---
title: PHP Tower of Hanoi
date: 2018-09-17 17:15:07
tags: [PHP, Algorithm]
---

```php
<?php
function hlt($n) {
  if ($n === 1) {
    return 1;
  }
  return 2* hlt($n - 1) + 1;
}

echo hlt(64);

```