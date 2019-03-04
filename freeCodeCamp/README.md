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


