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

```JavaScript
"use strict";
x = 3.14; // throws an error because x is not declared
```

## Arrow function

JavaScript has few things to define function. Subsitution variable. You can const instead of let or var.

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

```JavaScript
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

## Parameters
ES6 can use few things which is how to use parameters. 

### Default Parameter
First thing, ES6 can set default parameters for function.
```JavaScript
function greeting(name = "Anonymous") {
  return "Hello " + name;
}
console.log(greeting("John")); // Hello John
console.log(greeting()); // Hello Anonymous
```
If you wanna set default parameter, define insede the parenthesis.

### Rest Operator
Then, ES6 can use the Rest Operator which can get obtain unspecified number of arguments.
```JavaScript
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}

console.log(howMany(0, 1)); // You have passed 2 arguments
console.log(howMany(0, 1, 2)); // You have passed 3 arguments
console.log(howMany("string", null, [1, 2, 3], { })); // You have passed 4 arguments.
```

### Spread Operator
A Spread Operator to Evaluate Arrays In-Place
The ES5 code bellow uses `apply()`.

- [apply](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)

```JavaScript
var arr = [6, 89, 3, 45];
var maximus = Math.max.apply(null, arr); // returns 89
```

Then, From ES6 you can use spread operator which means same apply function.

```JavaScript
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr); // returns 89
```

## Data Structure
The ES6 has few new syntax.


### Object
Assignment to assign variables from objects

ES5
```JavaScript
var voxel = {x: 3.6, y: 7.4, z: 6.54 };
var x = voxel.x; // x = 3.6
var y = voxel.y; // y = 7.4
var z = voxel.z; // z = 6.54
```


ES6
```JavaScript
var voxel = {
    x: 3.6,
    y: 7.4,
    z: 6.54
};
const { x, y, z } = voxel; // x = 3.6, y = 7.4, z = 6.54
```

Another way, you can assign another name variables.
```JavaScript
var voxel = {
    x: 3.6,
    y: 7.4,
    z: 6.54
};
const { x : a, y : b, z : c } = voxel; // a = 3.6, b = 7.4, c = 6.54
```

As well, you can assign nested objects.
```JavaScript
const a = {
    start: { x: 5, y: 6},
    end: { x: 6, y: -9 }
};
const { start : { x: startX, y: startY }} = a;
console.log(startX, startY); // 5, 6
```


### Array
The how to assign array is same syntax.
```JavaScript
const [a, b] = [1, 2, 3, 4, 5, 6];
console.log(a, b); // 1, 2
```

You can chose the value.
```JavaScript
const [a, b,,, c] = [1, 2, 3, 4, 5, 6];
console.log(a, b, c); // 1, 2, 5
```

Assignment with the Rest Operator to reassign array.  
You can use the Rest Operator in array when you ressign the variable.
```JavaScript
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7];
console.log(a, b); // 1, 2
console.log(arr); // [3, 4, 5, 7]
```


Also if you use the function, you can use ressign inside function, too.
```JavaScript
const profileUpdate = (profileData) => {
  const { name, age, nationality, location } = profileData;
  // do something with these variables
}
```


## Template Literals
ES6 has new string literals. Wrapping backquote and using dollar mark and curly bracket.

```JavaScript
var name = "RyotArch";
var newString = `Hello my name is ${name}`;
document.write(newString);
```

```JavaScript
const person = {
  name: "Zodiac Hasbro",
  age: 56
};

// Template literal with multi-line and string interpolation
const greeting = `Hello, my name is ${person.name}!
I am ${person.age} years old.`;

console.log(greeting); // prints
// Hello, my name is Zodiac Hasbro!
// I am 56 years old.
```


Concise Object Literal Declarations.

```JavaScript
const getMousePosition = (x, y) => ({
    x: x,
    y: y
});

const getMousePosition = (x, y) => ({ x, y });
```

Write Concise Declarative Functions with ES6
```JavaScript
const person = {
  name: "RyotArch",
  sayHello() {
    return `Hello! My name is ${this.name}.`;
  }
};
console.log(person.sayHello());
```

## Class
You can use class from ES6.

### Constructor
The bellow code is class Syntax to Define a Constructor Function.
```JavaScript
class SpaceShuttle {
  constructor(targetPlanet){
    this.targetPlanet = targetPlanet;
  }
}
const zeus = new SpaceShuttle('Jupiter');
```

### Getter and Setter
ES6 can use capsulation. If you wanna use getter and setter, you can use `set` and `get` keyword before method name.
```JavaScript
class Person {
    constructor(name) {
        this._name = name;
    }

    get name() {
        return this._name.toUpperCase();
    }

    set name(newName) {
        this._name = newName;   // validation could be checked here such as only allowing non numerical values
    }

    sayHello() {
        console.log('Hello, my name is ' + this._name + '.');
    }
}
const person = new Person('RyotArch');
console.log(person.name);  // RYOTARCH
person.sayHello(); // Hello, my name is RyotArch.
```

## import and export

If you use a Node.js, you should use `require()`, but you use the ES6 code on browser.
You should `import`.
The import is you can require module code on another file. Also if you wanna import file, you have to export on imported file. In you use export, you have to `export default` keyword.

For example

module.js
```JavaScript
export default class Module(){
    sayHello(){
        console.loog("Hello");
    }
}
```

index.js
```JavaScript
import {sayHello} from './module.js';

sayHello();
```

If you use default, you don't need `as` keyword and mehotd name.

Same thing, you can use function or variable.
```JavaScript
const capitalizeString = (string) => {
  return string.charAt(0).toUpperCase() + string.slice(1);
}
const foo = "bar";
export { capitalizeString, foo }
```

In addtion, if you wanna use the all modules. Using the `import * as` syntax.
```JavaScript
import * as Module from './module.js';
```
