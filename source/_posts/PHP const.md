---
title: PHP Const
date: 2018-09-16 11:25:52
tags: [PHP]
---
## Const
- Use Uppercase
- System Constant
  - `PHP_VERSION`
  - `PHP_OS`
  - `PHP_INT_MAX`
- Customize (const is Global, can be scalar or array, define only once)
  - `define()` --> `define($name, $value)`
  - `const` key word
    - `const NAME = 'NAME';`
    - `const HELLO = 'HELLO WORLD!';`
- Get const value 
  - `const($const_name);`
- Check if const aleady exist
  - `defined($const_name);` --> return T/F
- Get all defined consts --> `get_define_constants()` --> return an array contains all defined constants
- Magic constants
  - `__LINE__	` --> line number
  - `__FILE__		` --> full directory and file name
  - `__DIR__	` --> full directory
  - `__FUNCTION__	` --> function name
  - `__CLASS__	` --> class name
  - `__TRAIT__	` --> trait name
  - `__METHOD__	` --> current function name inside current class
  - `__NAMESPACE__	` --> namespace name