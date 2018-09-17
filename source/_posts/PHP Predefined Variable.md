---
title: PHP Predefined Variable
date: 2018-09-17 11:15:07
tags: [PHP]
---

## What is a predefined variable?
- Global variable
- Provided by PHP
  
## Category
- `$GLOBALS` Including all below:
- `$_SERVERS` Server info
- `$_ENV` Environment info
- `$_COOKIE` Cookie info
- `$_SESSION` Session info
- `$_FILE` Upload file info
- `$_GET` HTTP GET info
  - Get data from `get`/search params/ ?format=234: `$_GET[param_name]` 
- `$_POST` HTTP POST info
  - Get data from `post`: `$_POST[input_name]` 
- `$_REQUEST` including post, get, cookie
  - `$_REQUEST[name]` 