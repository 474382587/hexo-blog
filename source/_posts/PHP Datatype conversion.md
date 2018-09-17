---
title: PHP Datatype conversion
date: 2018-09-14 15:19:58
tags: [PHP]
---

# 数据转换 Datatype conversion

1. 自动转换（隐式转换）Auto
2. 强制转换（显式转换）Setting
  
其他类型转换成数值型
```
1 + true = 2 // true  = 1
1 + false = 1 // false = 0
1 + null = 1 // null = 0
1 + 'string' = 1 // string = 0
1 + '21dasdas' = 22
1 + '2e2asda' = 201
```

falsy：
1. int,float 0
2. null
3. empty array
4. "" ''
5. string 0
