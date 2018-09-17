---
title: PHP Data Type Conversion
date: 2018-09-14 11:22:07
tags: [PHP]
---
## Temperary
- Integer: `(int|integer)$var;`
- Float: `(float|double|real)$var;`
- String: `(string)$var;`
- Boolean: `(bool|boolean)$var;`
- Null: `(unset)$var;`
- Array: `(array)$var;`
- Object: `(object)$var;`
---
- Integer: `intval($var);`
- Float: `floatval($var);`, `doubleval($var);`
- String: `strval($var);`
- Boolean: `boolvar($var);`
---

## Permanent
`sertype($var, 'type')` -- set data type
`gettype($var)` -- get data type`       
<pre>Types:
  1. boolean/bool
  2. integer/int
  3. string
  4. float
  5. array
  6. object
  7. null
</pre>

## Verify Data Type

```php
// -- is_*
is_int()
is_integer()
is_long()
is_float()
is_double()
is_real()
is_string()
is_bool()
is_scalar()
is_null()
is_array()
is_object()
is_resource()
is_numeric()
...
// return true | false
```