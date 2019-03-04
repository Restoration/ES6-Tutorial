# ES6 for freeCodeCamp

## Basic
Differences Between the `var` and `let` keywords. It is very simple thing which is diffrent scoped.
`var` is function scope, Conversely `let` is block scoped.
As well JavaScript has `const` variable which can define the immutable variable. The variable defined by const keywords is read-only. You can't chnage the value.


```JavaScript
let foo;
var foo;
const FOO;
```

`"use strict";` which means using strict mode. If you use this mode, you can use more polite syntax. Therefore browser accurate check the error.
i```JavaScript
"use strict";
x = 3.14; // throws an error because x is not declared
```

## Arrow function

JavaScript has few things to define function.

Subsitution variable. You can const instead of let or var.
```JavaScript
const myFunc = function() {
    const myVar = "value";
    return myVar;
}
```

The basic function declared.
```JavaScript
functin myFunc(){
    const myVar = "value";
    return myVar;
}
```

Arrow function
```JavaScript
const myFunc = () => {
    const myVar = "value";
    return myVar;
}
```

You can use arrow function from ES6.  

A bellow code is passing arguments.
```JavaScript
const myFunc = (myVar) => {
    return myVar;
}

// another way
const doubler = (item) => item * 2;
```

## Higher Order Arrow Functions
Arrow functions work really well with higher order functions, such as `map()`, `filter()`, and `reduce()`, that take other functions as arguments for processing collections of data.

These functions can loop process.
- [map](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- [filter](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- [reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

### map
You can create new array with map. And second argument and therd argument are optional.

```JavaScript
var array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]
```

### filter
You can get a data which matchs condition. And second argument and therd argument are optional.

```
var words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result);
// expected output: Array ["exuberant", "destruction", "present"]
```


### reduce
Get the value after process.
In this case, accumulator value means, it likes totaly result to previous.
```JavaScript
const array1 = [1, 2, 3, 4];
const reducer = (accumulator, currentValue) => accumulator + currentValue;

// 1 + 2 + 3 + 4
console.log(array1.reduce(reducer));
// expected output: 10

// 5 + 1 + 2 + 3 + 4
console.log(array1.reduce(reducer, 5));
// expected output: 15
```

Another way.
```JavaScript
const total = [0, 1, 2, 3].reduce(function(previousValue, currentValue, index, array) {
    return previousValue + currentValue;
});
console.log(total);
// expected output: 6
```

