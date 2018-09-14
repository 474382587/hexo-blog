---
title: CSS white-space
date: 2018-06-03 15:00:34
tags:
---

# white-space

## /* Keyword values */
white-space: normal;    
white-space: nowrap;    
white-space: pre;    
white-space: pre-wrap;    
white-space: pre-line;    

## /* Global values */    
white-space: inherit;     
white-space: initial;     
white-space: unset;      


### normal    
Sequences of whitespace are collapsed. Newline characters in the source are handled the same as other whitespace. Lines are broken as necessary to fill line boxes.
### nowrap
Collapses whitespace as for normal, but suppresses line breaks (text wrapping) within the source.
### pre
Sequences of whitespace are preserved. Lines are only broken at newline characters in the source and at <br> elements.
### pre-wrap
Sequences of whitespace are preserved. Lines are broken at newline characters, at <br>, and as necessary to fill line boxes.
### pre-line
Sequences of whitespace are collapsed. Lines are broken at newline characters, at <br>, and as necessary to fill line boxes.


There are some cases that you will need to use nowrap:
1. Navigation menu items     
  If the screen size is getting smaller and the width for each navigation link text is not enough to show all word in a single line
2. When you want to have "..."
  For example:
    ```
    overflow: hidden;
	white-space: nowrap;
	text-overflow: ellipsis;
    ```
























Reference: https://developer.mozilla.org/en-US/docs/Web/CSS/white-space
