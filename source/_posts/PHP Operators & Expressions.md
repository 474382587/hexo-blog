---
title: PHP Operators & Expressions
date: 2018-09-17 11:33:07
tags: [PHP]
---

## Operators
- Arithmatic Operators
  - `+  -  *   /  %`, PHP7 --> `**` (power of)
  - increment/decrement
    - ++$var
    - --$var
    - $var--
    - $var++
    - Types
      - float --> yes
      - int --> yes
      - bool --> not support this operator
      - null --> only support increment
      - string --> only support increment --> last character
      - get ASCII code `ord($str)`
      - get Character based on ASCII code `chr(98)`

---
- String Operators
  - Concatenation Operator --> `.`
    - `$str1.$str2.$str3`
---
- Assignment Operators
  - Example:
    ```php
    $a = 3; 
    $a += 5; // sets $a to 8, as if we had said: $a = $a + 5;
    $b = "Hello ";
    $b .= "There!"; // sets $b to "Hello There!", just like $b = $b . "There!"; 
    ```
---
- Compare Operators
  - Return boolean value
  - Example:
    ```php
    $a == $b	// Equal	TRUE if $a is equal to $b after type juggling.
    $a === $b	// Identical	TRUE if $a is equal to $b, and they are of the same type.
    $a != $b	// Not equal	TRUE if $a is not equal to $b after type juggling.
    $a <> $b	// Not equal	TRUE if $a is not equal to $b after type juggling.
    $a !== $b	   // Not identical	TRUE if $a is not equal to $b, or they are not of the same type.
    $a < $b	      // Less than	TRUE if $a is strictly less than $b.
    $a > $b	      // Greater than	TRUE if $a is strictly greater than $b.
    $a <= $b	// Less than or equal to	TRUE if $a is less than or equal to $b.
    $a >= $b	// Greater than or equal to	TRUE if $a is greater than or equal to $b.
    $a <=> $b	// Spaceship	An integer less than, equal to, or greater than zero when $a is respectively less than, equal to, or greater than $b. Available as of PHP 7.
    $a ?? $b ?? $c // null detection, if not null, return not null value --> PHP 7
    ```

---
- Logic Operators
  - Examples:
    ```php
    $a and $b	// And	TRUE if both $a and $b are TRUE.
    $a or $b	// Or	TRUE if either $a or $b is TRUE.
    $a xor $b	// Xor	TRUE if either $a or $b is TRUE, but not both.
    ! $a	        // Not	TRUE if $a is not TRUE.
    $a && $b	// And	TRUE if both $a and $b are TRUE.
    $a || $b	// Or	TRUE if either $a or $b is TRUE.
    ```
---
  - Error Control Operators
    - `@` 
    - Add this `@` before any expression that will lead to an error --> error message will not show up

---
- Ternary Operator
  - `condition ? satisfied : not satisfied`

---
## Operator Precedence 
```php
    non-associative	//clone new	clone and new
    left	//[	array()
    right	//**	arithmetic
    right	//++ -- ~ (int) (float) (string) (array) (object) (bool) @	types and increment/decrement
    non-associative   //instanceof	types
    right	//!	logical
    left	//* / %	arithmetic
    left	//+ - .	arithmetic and string
    left	//<< >>	bitwise
    non-associative	//< <= > >=	comparison
    non-associative	//== != === !== <> <=>	comparison
    left	//&	bitwise and references
    left	//^	bitwise
    left	//|	bitwise
    left	//&&	logical
    left	//||	logical
    right	//??	comparison
    left	//? :	ternary
    right	//= += -= *= **= /= .= %= &= |= ^= <<= >>=	assignment
    left	//and	logical
    left	//xor	logical
    left	//or	logical


```