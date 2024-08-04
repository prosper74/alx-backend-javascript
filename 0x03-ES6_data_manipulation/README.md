# ES6 data manipulation

### Map, Filter, and Reduce on Arrays
- **Map:** map creates a new array by applying a function to each element of the original array.
```
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
console.log(doubled); // [2, 4, 6, 8]
```

- **Filter:** filter creates a new array with all elements that pass the test implemented by the provided function.
```
const numbers = [1, 2, 3, 4];
const even = numbers.filter(num => num % 2 === 0);
console.log(even); // [2, 4]
```

- **Reduce:** reduce applies a function against an accumulator and each element in the array to reduce it to a single value.
```
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((accumulator, currentValue) => accumulator + currentValue, 0);
console.log(sum); // 10
```

### Typed Arrays
Typed Arrays are array-like objects that provide a mechanism for reading and writing raw binary data in memory buffers. They are useful for handling binary data, such as when working with WebGL or file I/O in a more efficient manner.

- **ArrayBuffer:** A generic, fixed-length binary data buffer.
```
const buffer = new ArrayBuffer(16); // create a buffer of 16 bytes
```

- **Typed Array Views:** Views such as Uint8Array, Int32Array, Float64Array, etc., allow you to read and write the contents of an ArrayBuffer.
```
const buffer = new ArrayBuffer(16);
const view = new Uint8Array(buffer);
view[0] = 255;
console.log(view[0]); // 255
```

### Set, Map, and Weak Data Structures
- **Set:**  Set is a collection of unique values.
``
const set = new Set([1, 2, 3, 3]);
set.add(4);
console.log(set); // Set(4) { 1, 2, 3, 4 }
set.delete(2);
console.log(set); // Set(3) { 1, 3, 4 }
```

- **Map:** A Map is a collection of key-value pairs where the keys can be of any type.
``
const map = new Map();
map.set('a', 1);
map.set('b', 2);
console.log(map.get('a')); // 1
map.delete('b');
console.log(map.has('b')); // false
```

- **WeakSet:** A WeakSet is similar to a Set, but it only holds weak references to its objects, meaning they can be garbage collected if there are no other references to them.
```
const weakSet = new WeakSet();
let obj = {a: 1};
weakSet.add(obj);
console.log(weakSet.has(obj)); // true
obj = null; // The object may now be garbage collected
```

- **WeakMap:** A WeakMap is similar to a Map, but it only holds weak references to its keys, meaning they can be garbage collected if there are no other references to them.
```
const weakMap = new WeakMap();
let keyObj = {};
weakMap.set(keyObj, 'value');
console.log(weakMap.get(keyObj)); // 'value'
keyObj = null; // The key object may now be garbage collected
```

These ES6 features provide powerful tools for working with data structures and manipulating arrays in JavaScript, allowing for more efficient and concise code.