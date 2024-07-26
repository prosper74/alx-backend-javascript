# ES6 Overview
ES6, also known as ECMAScript 2015 or ES2015, is a significant update to JavaScript that introduced a variety of new features aimed at making the language more powerful and easier to work with. It is the sixth edition of the ECMAScript language specification.

## New Features Introduced in ES6
- Block-Scoped Variables (let and const)
- Arrow Functions
- Classes
- Template Literals
- Destructuring Assignment
- Default Parameters
- Rest and Spread Operators
- Enhanced Object Literals
- Promises
- Iterators and for-of Loops
- Modules
- Map and Set

### Differences Between a Constant and a Variable
**Variable (let/var):**
- Declared using let or var.
- Can be reassigned.
- let is block-scoped, while var is function-scoped.

**Constant (const):**
- Declared using const.
- Cannot be reassigned.
- Block-scoped like let.
- The value itself is not immutable; objects or arrays declared with const can have their contents modified.

```
let variable = 10;
variable = 20; // Allowed

const constant = 10;
constant = 20; // Error: Assignment to constant variable
```

### Block-Scoped Variables
Variables declared with let and const are block-scoped, meaning they are only accessible within the block, statement, or expression where they are defined.

```
{
  let x = 10;
  const y = 20;
  console.log(x); // 10
  console.log(y); // 20
}
// console.log(x); // Error: x is not defined
// console.log(y); // Error: y is not defined
```

### Arrow Functions
Arrow functions provide a concise syntax to write function expressions. They also lexically bind the this value, which means this inside an arrow function refers to the this value of the enclosing execution context.

```
const add = (a, b) => a + b;
console.log(add(2, 3)); // 5

// Function parameters with default values
const multiply = (a, b = 1) => a * b;
console.log(multiply(2)); // 2 (2 * 1)
```

### Rest and Spread Function Parameters
Rest Parameters: Allow you to represent an indefinite number of arguments as an array.

```
const sum = (...numbers) => {
  return numbers.reduce((acc, number) => acc + number, 0);
};
console.log(sum(1, 2, 3, 4)); // 10
```

**Spread Operator:** Allows an iterable (like an array) to be expanded in places where zero or more arguments (for function calls) or elements (for array literals) are expected.

```
const arr = [1, 2, 3];
const newArr = [...arr, 4, 5];
console.log(newArr); // [1, 2, 3, 4, 5]
```

### String Templating in ES6
Template literals provide an easy way to create multi-line strings and concatenate variables and expressions into strings.

```
const name = 'John';
const greeting = `Hello, ${name}!`;
console.log(greeting); // Hello, John!
```

### Object Creation and Properties in ES6
ES6 introduces shorthand syntax for creating objects and defining methods.

```
const name = 'John';
const age = 30;

const person = {
  name,
  age,
  greet() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

person.greet(); // Hello, my name is John
```

### Iterators and for-of Loops
**Iterators:** An object that provides a next() method which returns { value, done } pairs.
**for-of Loop:** Iterates over iterable objects like arrays, strings, maps, sets, etc.

```
const arr = [1, 2, 3, 4, 5];
for (const num of arr) {
  console.log(num);
}
// 1
// 2
// 3
// 4
// 5
```
