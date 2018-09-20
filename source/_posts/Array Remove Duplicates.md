---
title: JavaScript Array Remove Duplicates
date: 2018-09-19 22:47:34
tags: [JavaScript, Algorithm]
---

```javascript
let aa = [
  {
    name: '1',
    age: 18
  },
  {
    name: '2',
    age: 12
  },
  {
    name: '3',
    age: 18
  },
  {
    name: '4',
    age: 18
  }
]

let hash = {}
let b = aa.reduce((acc, current) => {
  if (!hash[current.age]) {
    console.log(acc)
    hash[current.age] = 1
    acc.push(current)
    return acc
  }
  return acc
}, [])
```
