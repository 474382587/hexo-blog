---
title: Regular Expression
date: 2018-08-11 21:33:21
tags:
---

# Regex

> Regular expressions are used in programming languages to match parts of strings. 

One way to test a regex is using the .test() method.     
The `test()` method executes a search for a match between a regular expression and a specified string. Returns true or false.
```
var regex1 = RegExp('foo*');
var regex2 = RegExp('foo*','g');
var str1 = 'table football';

console.log(regex1.test(str1));
// expected output: true

console.log(regex1.test(str1));
// expected output: true

console.log(regex2.test(str1));
// expected output: true

console.log(regex2.test(str1));
// expected output: false

```

- It is Case sensitive --> `/big/` is not equavalent to `/Big/` or `/BIG/`
- You can search for multiple patterns using the alternation or OR operator: |.
- **Ignore Case**:  use i flag to make it not case sensitive `/big/i` for big, Big, BIG
- **Extract Matches**: .match() method --> match exact REGEX and extract      
``` var paragraph = 'The quick brown fox jumped over the lazy dog. It barked.';
var regex = /[A-Z]/g;
var found = paragraph.match(regex);

console.log(found);
// expected output: Array ["T", "I"]
```
- To search or extract a pattern more than once, you can use the g flag.
- The wildcard character . will match any one character. The wildcard is also called dot and period `/re./` --> reg, ref, reh ...
-  Match Single Character with Multiple Possibilities --> For example, you want to match "bag", "big", and "bug" but not "bog". You can create the regex /b[aiu]g/ to do this. The [aiu] is the character class that will only match the characters "a", "i", or "u".
- [a-z] -- [0-9] -- [A-Z] these are character classes
- To create a negated character set, you place a caret character (^) after the opening bracket and before the characters you do not want to match. --> [^0-9]
- Use the + character to finding repeating --> /[0-9]+/, /a+/ `+` means 1 or more
- `*` means 0 or more

- 
