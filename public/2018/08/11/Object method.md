```
// OBJ
var A = {
  print: function () {
    console.log('hello');
  }
};

// OBJ
var B = Object.create(A);

Object.getPrototypeOf(B) === A // true
B.print() // hello
B.print === A.print // true
```
