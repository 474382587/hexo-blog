---
title: PHP Array
date: 2018-09-19 22:57:34
tags: [PHP, Array]
---

# Array
---
Create Array
- `array();`
- `array(2,3,4,'king',true)`
**$arr = array(key=>value)**
> The key can either be an integer or a string. The value can be of any type.
> If multiple elements in the array declaration use the same key, only the last one will be used as all others are overwritten.


  ```php
  // simple array
  <?php
  $array = array(
      "foo" => "bar",
      "bar" => "foo",
  );

  // as of PHP 5.4
  $array = [
      "foo" => "bar",
      "bar" => "foo",
  ];
  ?>

  // Type Casting and Overwriting example
  <?php
  $array = array(
      1    => "a",
      "1"  => "b",
      1.5  => "c",
      true => "d",
  );
  var_dump($array);
  ?>

  // Example #3 Mixed integer and string keys
  <?php
  $array = array(
      "foo" => "bar",
      "bar" => "foo",
      100   => -100,
      -100  => 100,
  );
  var_dump($array);
  ?>
  ```
1. array()
2. array(value,...)
3. array(key=>value,...)
4. []
---
#### Check if a variable is array
1. var_dum() --> visually see it 
2. gettype() --> visually see it 
3. is_array()

#### Key Name
1. String or integer
2. Others will be converted to integer
    1. boolean --> true -> 1 false -> 0
    2. null -> empty string ''
3. Duplicate key name -> only keep the last one
4. If no key name: from 0 (if key name is minus goes from 0)
---
Multidimensional Array 
```php
$arr1 = array (
  array(1,2,3,4),
  array(2,3,4,5)
);

$arr2 = array(
  array('id'=>1,'name'=>2,3,4),
  array(1,2,3,4),
);

$arr3 = array(
  array('id'=>1,'name'=>2,3,4),
  'next'=>array(1,2,3,4),
);
```
```php
$arr1[]=12;
$arr1[]=13;
$arr1[]=14;
$arr1[]=11;
// array(12,13,14,11);

$arr2[3] = 45;
$arr2[] = 45;
$arr2['hi'] = 45;
$arr2[-3] = 45;
// array(3=>45, 45, 'hi'=>45, -3=>45)

```

---
`range($start, $end, $increment)`
```php
range(1,10); // 1, 2, 3, 4, ... 10
range('a','z'); // a,...,z
```

`compact($variable1,...)` 
```php
$name = "name";
$age = 33;
$arr = compact('name','age');
```