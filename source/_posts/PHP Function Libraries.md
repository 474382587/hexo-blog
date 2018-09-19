---
title: PHP Function Libraries
date: 2018-09-18 10:59:07
tags: [PHP]
---

## Internal Functions

### Common String Functions

- `strlen($string)` --> get string length
- `strtoupper($string)` --> convert to uppercase
- `strtolower($string)` --> convert to lowercase
- `ucfirst($string)` --> first letter of the string to be uppercase
- `ucwords($string)` --> first letter of every words to be uppercase
- `str_replace(mixed $search , mixed $replace , mixed $subject [, int &$count ])`

  ```php
  /*
  **search**
    The value being searched for, otherwise known as the needle. An array may be used to designate multiple needles.

  **replace**
    The replacement value that replaces found search values. An array may be used to designate multiple replacements.

  **subject**
    The string or array being searched and replaced on, otherwise known as the haystack.

    If subject is an array, then the search and replace is performed with every entry of subject, and the return value is an array as well.

  **count**
    If passed, this will be set to the number of replacements performed.
  */
  ```

- `str_ireplace( mixed $search , mixed $replace , mixed $subject [, int &$count ] )`

  ```php
  /*
    search
      The value being searched for, otherwise known as the needle. An array may be used to designate multiple needles.

    replace
      The replacement value that replaces found search values. An array may be used to designate multiple replacements.

    subject
      The string or array being searched and replaced on, otherwise known as the haystack.

      If subject is an array, then the search and replace is performed with every entry of subject, and the return value is an array as well.

    count
      If passed, this will be set to the number of replacements performed.
  */
  ```

- `htmlspecialchars( string $string [, int $flags = ENT_COMPAT | ENT_HTML401 [, string $encoding = ini_get("default_charset") [, bool $double_encode = TRUE ]]] )` --> html special characters --> such that:
- > & (ampersand) ------------ \&amp;  
  >  " (double quote) ------------ \&quot;, unless ENT_NOQUOTES is set  
  >  ' (single quote) ------------ \&#039; (for ENT_HTML401) or \&apos; (for ENT_XML1, ENT_XHTML or ENT_HTML5), but only when ENT_QUOTES is set  
  >  < (less than) ------------ \&lt;  
  >  \> (greater than) ------------ \&gt;
  ```php
  /*
    ENT_COMPAT	Will convert double-quotes and leave single-quotes alone.
    ENT_QUOTES	Will convert both double and single quotes.
    ENT_NOQUOTES	Will leave both double and single quotes unconverted.
    ENT_IGNORE	Silently discard invalid code unit sequences instead of returning an empty string. Using this flag is discouraged as it » may have security implications.
    ENT_SUBSTITUTE	Replace invalid code unit sequences with a Unicode Replacement Character U+FFFD (UTF-8) or &#xFFFD; (otherwise) instead of returning an empty string.
    ENT_DISALLOWED	Replace invalid code points for the given document type with a Unicode Replacement Character U+FFFD (UTF-8) or &#xFFFD; (otherwise) instead of leaving them as is. This may be useful, for instance, to ensure the well-formedness of XML documents with embedded external content.
    ENT_HTML401	Handle code as HTML 4.01.
    ENT_XML1	Handle code as XML 1.
    ENT_XHTML	Handle code as XHTML.
    ENT_HTML5	Handle code as HTML 5.
  */
  ```
- `ltrim ( string $str [, string $character_mask ] )` --> trim specific character from the left(beginning) --> will trim all \s if not specified
- `rtrim ( string $str [, string $character_mask ] )` --> trim specific character from the right(end) --> will trim all \s if not specified
- `trim ( string $str [, string $character_mask ] )` --> trim specific character from both side --> will trim all \s if not specified
- `strrpos($string2, $string1$)` --> return the postion where string1 is last occurred in string2 (case sensitive))
- `strripos($string2, $string1$)` --> return the postion where string1 last occurred in string2 (not case sensitive)
- `substr( string $string , int $start [, int $length ] )` --> Returns the portion of string specified by the start and length parameters.
- `strstr( string $haystack , mixed $needle [, bool $before_needle = FALSE ] )` --> Find the first occurrence of a string --> Returns part of haystack string starting from and including the first occurrence of needle to the end of haystack.

  ```php
    <?php
    $email  = 'name@example.com';
    $domain = strstr($email, '@');
    echo $domain; // prints @example.com

    $user = strstr($email, '@', true); // As of PHP 5.3.0
    echo $user; // prints name
    ?>
  ```

- `strrev()` --> Returns string, reversed.

- `md5( string $str [, bool $raw_output = FALSE ] )` --> alculates the MD5 hash of str using the » RSA Data Security, Inc. MD5 Message-Digest Algorithm, and returns that hash.
- `str_shuffle($string)` --> str_shuffle() shuffles a string. One permutation of all possible is created.
- `explode( string $delimiter , string $string [, int $limit = PHP_INT_MAX ] )` --> Returns an array of strings, each of which is a substring of string formed by splitting it on boundaries formed by the string delimiter.


    ```php
    /*
    delimiter
      The boundary string.

    string
      The input string.

    limit
      If limit is set and positive, the returned array will contain a maximum of limit elements with the last element containing the rest of string.

      If the limit parameter is negative, all components except the last -limit are returned.

      If the limit parameter is zero, then this is treated as 1.
    */
    <?php
    // 1
    $pizza  = "piece1 piece2 piece3 piece4 piece5 piece6";
    $pieces = explode(" ", $pizza);
    echo $pieces[0]; // piece1
    echo $pieces[1]; // piece2

    // 2
    $data = "foo:*:1023:1000::/home/foo:/bin/sh";
    list($user, $pass, $uid, $gid, $gecos, $home, $shell) = explode(":", $data);
    echo $user; // foo
    echo $pass; // *
    ?>
    ```

- `implode( string $glue , array $pieces ) | string implode ( array $pieces )` --> Join array elements with a glue string.
- `sprintf( string $format [, mixed $args [, mixed $... ]] )` --> Returns a string produced according to the formatting string format.

---

### Common Math Functions

- `ceil( float $value )` --> Returns the next highest integer value by rounding up value if necessary. -> Round fractions up
- `floor ( float $value )` --> Returns the next lowest integer value (as float) by rounding down value if necessary. --> floor — Round fractions down

- `pow ( number $base , number $exp )` --> Returns base raised to the power of exp.
- `sqrt ( float $arg )` --> The square root of arg or the special value NAN for negative numbers.
- `max ( array $values )` --> min value
- `min(array $values)` --> max value
- `rand() | rand ( int $min , int $max )` --> random number
- `mt_rand() | mt_rand ( int $min , int $max )` --> mt_rand — Generate a random value via the Mersenne Twister Random Number Generator -- random number
- 
---

## User Functions
