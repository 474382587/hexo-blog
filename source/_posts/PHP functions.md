---
title: PHP Functions
date: 2018-09-17 11:15:07
tags: [PHP]
---

# Functions

## Declare function

```php
function echoDragon() {
  // code
}
// call function
echoDragon();
```

---

## Naming Convention

- Alphabet, underscore, number
- Number cannot be first letterc

---

## Parameters

```php
function sum($a, $b) {
  echo $a + $b
}
// call function
sum(1,2);
```

---

## Return Value

```php
function sum($a, $b) {
  return $a + $b
}
// call function
echo sum(1,2);
```

---

## **Variable scope**

```php
<?php
$a = 1; /* global scope */

function test()
{
    echo $a; /* reference to local scope variable */
}

test();
?>
```

- `global` keyword

  ```PHP
    <?php
    $a = 1;
    $b = 2;

    function Sum()
    {
        global $a, $b;

        $b = $a + $b;
    }

    Sum();
    echo $b;
    ?>
  ```

- `$GLOBALS`

  ```php
    <?php
    $a = 1;
    $b = 2;

    function Sum()
    {
        $GLOBALS['b'] = $GLOBALS['a'] + $GLOBALS['b'];
    }

    Sum();
    echo $b;
    ?>
  ```

- `static local variable` --> if defined, use previous value
  ```php
    function local() {
      static $var = 1;
      $var++;
      echo $var;
    }
    local(); // echo 2
    local(); // echo 3
    echo $var; // error message
  ```
- `dynamic local variable`
  ```php
    function local() {
      $var = 1;
      $var++;
      echo $var;
    }
    local(); // echo 2
    local(); // echo 2
    echo $var; // error message
  ```

---

## Passing by Reference & Passing by Value

```php
// by Reference
<?php
$a = 3;
function change(&$c) {
  $c = 33;
}

change($a);
echo $a; // 33
?>

---

<?php
// by Value
$a = 3;
function change(&$c) {
  $c = 33;
}

change($a);
echo $a; // 33
?>
```

> **Note**: if passing an object/array, it is actually passing address instead of value by default!

---

## Default Parameter Value

```php
<?php
function echoValue($b, $a = 3) {
  echo $a;
}
echoValue(2); // echo 3, a will take default value 3
?>
```

---

## Argument Functions

- `func_num_args` --> return amount of total paramenter
- `func_get_args` --> return all parameters as an array

---

## Argument Type

```php
// 3 type checks -> Array, Object, Callback
function needArray(array arr) {
  return arr;
}

needArr('ss'); // error --> type error

// callback will be passed by a string
needArr('callback_function_name');
```

---

## Variable Function

```php
function test() {
  return 1;
}

$func = 'test';

// always do this
if(is_callable($func)){ // check if this variable function is callable to prevent error
  $func(); // equal to test();
}

// or

if (funtion_exists($func)) { // check if this variable function exists to prevent error
  $func(); // equal to test();
}
```

---

## Inner Function

```php
// Inner function has global scope
function foo() {
  function bar() {
    echo 'hello world!'
  }
}

foo(); // 'hello world!'
bar(); // 'hello world!'
```

---

## Variable Scope of Inner Function

```php
// Inner function has global scope
function foo() {
  $a = 3;
  function bar() {
    echo 'hello world!'
    echo $a; // error --> $a is not defined in this scope
  }
}

foo(); // 'hello world!'
bar(); // 'hello world!'
```

---

## Recursion

```php
// example 1
function sum($n, $m) {
  if ($m <= $n) {
    return $n;
  }
  return sum($n, $m - 1) + $m
}
echo sum(1, 100) // 5050

// example 2
function fbnq($n) {
  if ($n <= 2) {
    return 1;
  }
  else {
    return fbnq($n-1) + fbnq($n-2);
  }
}
echo fbnq(6) // 8
```

---

## Anonymous Function

```php
$say = function($str) {
  echo $str;
}; // this is treated as an statement --> need semicolon

$say('hello');
```

---

## Inner Function Access Parent Function Variable

```php
function test() {
  $a = 4;
  $say = function($str) use (&$a) { // add & to pass address or simply pass value
    echo $str;
    echo $message;
  }; // this is treated as an statement --> need semicolon
}

$say('hello'); // str and a

```
