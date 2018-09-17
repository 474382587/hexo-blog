---
title: PHP Day 1
date: 2018-09-14 11:15:07
tags: [PHP]
---

# PHP Day 1

## Why PHP?

1. Easy
2. Suitable for WEB development
3. WordPress
4. Large user group
5. Compatablility - Server - Database

## What for?

1. Interactive websites

## How to study PHP?

- 3W1H1P
  - What is it?
  - Why would I learn it?
  - When can I use it?
  - How to use it?
  - Practice it.

---

## Learn to code

- Practice more
- Think more
- Ask more

## PHP Development Environment

- LAMP - Linux + Apache + MySQL + PHP
- LNMP - Linux + Nginx + MySQL + PHP
- LNMPA - Linux + Nginx + MySQL + PHP + Apache
- WAMP - Window + Apache + MySQL + PHP

---

## PHP Syntax

- Extension: .php, **cannot use special characters**
- PHP style:
  - standard: <?php code; ?>
  - Short Open tag: <? code; ?>
  - ASP: <% code; %>
- If only `PHP` code inside a file, `?>` should be omitted
- `;` after each line of code
- comments
  - single line: 1. `// code` 2. `# code`
  - multiple lines: `/* code */`

## Variable

- Decalare a variable: `$variable_name;`, `$number = 1;`
- Start with `alphabet or _, no special characters`
- Camel case: `helloWord`
- Underscore: `hello_world`
- Case sensitive
- Variable variables: `<?php $a = 'hello'; $$a = 'world'; echo $$a . '<br />'; echo "$a ${$a} <br />`
- Variable types:
  - Int
    - decimal
    - hex
    - oct
    - binary
    - signed
    - unsigned
  -Float
    - scientific
    - .number
    - has error --> don't compare 2 float values
  - Boolean
    - true
    - false
  - String
    - single quote --> what you entered is what you will get except \', \\
      - `"$var this variable will not be showing up"`
    - double quote
      - `"$var this variable will be showing up"`
    - heredoc
      - ```$str = <<<EOF string_paragraph EOF;``` --> ""
    - nowdoc
      - ```$str = <<<EOF string_paragraph EOF;``` --> ''
  - Array
  - Object
  - Resource
  - null -- undefined variable or assigned to be null or `unset()` --> discard variable value
- `var_dump($var);` --> info about this variable
- `header` --> `header()`
- `\n` --> new line, `\r` --> enter, `\t` --> tab, `\\` --> \, `\'` --> ', `\"` --> " 
- {} --> `$string = 'abc';`