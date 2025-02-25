# JavaScript Core Methods Reference

## Array Methods

### 1. `map(callback(element, index, array), thisArg)`
Creates a new array by applying a function to each element.

```javascript
// Basic usage
const numbers = [1, 2, 3, 4];
const doubled = numbers.map(num => num * 2);
// Result: [2, 4, 6, 8]

// Using all parameters
const withIndexes = numbers.map((num, index, arr) => {
  return `Element ${num} at index ${index} in array ${arr}`;
});

// With thisArg
const multiplier = { value: 3 };
const tripled = numbers.map(function(num) {
  return num * this.value;
}, multiplier);
// Result: [3, 6, 9, 12]
```

### 2. `filter(callback(element, index, array), thisArg)`
Creates a new array with elements that pass a test.

```javascript
const numbers = [1, 2, 3, 4, 5, 6];
const evens = numbers.filter(num => num % 2 === 0);
// Result: [2, 4, 6]

// With index
const filteredByIndex = numbers.filter((num, index) => index > 2);
// Result: [4, 5, 6]

// With thisArg
const threshold = { min: 3 };
const aboveThreshold = numbers.filter(function(num) {
  return num > this.min;
}, threshold);
// Result: [4, 5, 6]
```

### 3. `reduce(callback(accumulator, currentValue, index, array), initialValue)`
Reduces array to a single value by applying a function.

```javascript
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce((acc, curr) => acc + curr, 0);
// Result: 10

// Without initialValue (first element becomes initialValue)
const product = numbers.reduce((acc, curr) => acc * curr);
// Result: 24 (starts with 1 as accumulator)

// More complex example with all parameters
const items = [
  { name: 'Item 1', price: 10 },
  { name: 'Item 2', price: 20 },
  { name: 'Item 3', price: 30 }
];
const cartTotal = items.reduce((total, item, index, arr) => {
  console.log(`Processing item ${index + 1}/${arr.length}`);
  return total + item.price;
}, 0);
// Result: 60
```

### 4. `forEach(callback(element, index, array), thisArg)`
Executes a function on each element (no return value).

```javascript
const fruits = ['apple', 'banana', 'cherry'];
fruits.forEach((fruit, index) => {
  console.log(`${index}: ${fruit}`);
});
// Output:
// 0: apple
// 1: banana
// 2: cherry

// With thisArg
const logger = {
  prefix: 'Fruit',
  log: function(fruits) {
    fruits.forEach(function(fruit, index) {
      console.log(`${this.prefix} ${index + 1}: ${fruit}`);
    }, this);
  }
};
logger.log(fruits);
// Output:
// Fruit 1: apple
// Fruit 2: banana
// Fruit 3: cherry
```

### 5. `find(callback(element, index, array), thisArg)`
Returns first element that passes a test.

```javascript
const numbers = [5, 12, 8, 130, 44];
const found = numbers.find(num => num > 10);
// Result: 12

// With all parameters
const foundWithIndex = numbers.find((num, index, arr) => {
  console.log(`Checking ${num} at index ${index}`);
  return num > 100;
});
// Result: 130

// With thisArg
const criteria = { threshold: 40 };
const foundWithThisArg = numbers.find(function(num) {
  return num > this.threshold;
}, criteria);
// Result: 44
```

### 6. `findIndex(callback(element, index, array), thisArg)`
Returns index of first element that passes a test.

```javascript
const numbers = [5, 12, 8, 130, 44];
const foundIndex = numbers.findIndex(num => num > 10);
// Result: 1 (index of 12)

// With thisArg
const criteria = { threshold: 100 };
const largeNumberIndex = numbers.findIndex(function(num) {
  return num > this.threshold;
}, criteria);
// Result: 3 (index of 130)
```

### 7. `some(callback(element, index, array), thisArg)`
Tests if any element passes a test.

```javascript
const numbers = [1, 2, 3, 4, 5];
const hasEven = numbers.some(num => num % 2 === 0);
// Result: true

// With thisArg
const criteria = { threshold: 10 };
const hasLargeNumber = numbers.some(function(num) {
  return num > this.threshold;
}, criteria);
// Result: false
```

### 8. `every(callback(element, index, array), thisArg)`
Tests if all elements pass a test.

```javascript
const numbers = [2, 4, 6, 8, 10];
const allEven = numbers.every(num => num % 2 === 0);
// Result: true

// With all parameters
const allPositive = numbers.every((num, index, arr) => {
  console.log(`Checking ${num} at position ${index}`);
  return num > 0;
});
// Result: true
```

### 9. `includes(searchElement, fromIndex)`
Checks if array includes a certain element.

```javascript
const fruits = ['apple', 'banana', 'cherry'];
const hasBanana = fruits.includes('banana');
// Result: true

// With fromIndex
const hasAppleFromIndex1 = fruits.includes('apple', 1);
// Result: false (starts searching from index 1)
```

### 10. `slice(start, end)`
Returns selected elements as new array.

```javascript
const animals = ['ant', 'bison', 'camel', 'duck', 'elephant'];
const selected = animals.slice(1, 4);
// Result: ['bison', 'camel', 'duck']

// Negative indexes (count from end)
const lastTwo = animals.slice(-2);
// Result: ['duck', 'elephant']

// Without end parameter
const fromSecond = animals.slice(1);
// Result: ['bison', 'camel', 'duck', 'elephant']
```

### 11. `splice(start, deleteCount, item1, item2, ...)`
Adds/removes elements from array (modifies original).

```javascript
const months = ['Jan', 'March', 'April', 'June'];
// Insert at index 1
months.splice(1, 0, 'Feb');
// Result: ['Jan', 'Feb', 'March', 'April', 'June']

// Replace 2 elements at index 3
months.splice(3, 2, 'May');
// Result: ['Jan', 'Feb', 'March', 'May']

// Remove elements
const removed = months.splice(1, 2);
// months becomes ['Jan', 'May']
// removed contains ['Feb', 'March']
```

### 12. `sort(compareFunction)`
Sorts elements of array.

```javascript
const fruits = ['cherries', 'apples', 'bananas'];
fruits.sort();
// Result: ['apples', 'bananas', 'cherries']

// With compareFunction for numbers
const numbers = [1, 30, 4, 21, 100000];
numbers.sort((a, b) => a - b);
// Result: [1, 4, 21, 30, 100000]

// Custom comparison for objects
const items = [
  { name: 'Edward', value: 21 },
  { name: 'Sharpe', value: 37 },
  { name: 'And', value: 45 }
];
items.sort((a, b) => a.value - b.value);
// Result: sorted by value in ascending order
```

## String Methods

### 1. `split(separator, limit)`
Splits string into array of substrings.

```javascript
const str = 'The quick brown fox jumps over the lazy dog.';
const words = str.split(' ');
// Result: ['The', 'quick', 'brown', 'fox', 'jumps', 'over', 'the', 'lazy', 'dog.']

// With limit
const firstThreeWords = str.split(' ', 3);
// Result: ['The', 'quick', 'brown']

// Split by character
const chars = str.split('');
// Result: ['T', 'h', 'e', ' ', 'q', 'u', 'i', 'c', 'k', ...]

// Split by regex
const sentence = str.split(/\s+/);
// Splits by any whitespace
```

### 2. `substring(startIndex, endIndex)`
Extracts characters between two indices.

```javascript
const str = 'Mozilla';
const sub1 = str.substring(1, 3);
// Result: 'oz'

// If start > end, parameters are swapped
const sub2 = str.substring(3, 1);
// Result: 'oz' (same as above)

// With single parameter (extracts to end)
const sub3 = str.substring(2);
// Result: 'zilla'
```

### 3. `slice(startIndex, endIndex)`
Extracts part of string.

```javascript
const str = 'The morning is upon us.';
const sliced1 = str.slice(4, 11);
// Result: 'morning'

// Negative indices (count from end)
const sliced2 = str.slice(-3);
// Result: 'us.'

const sliced3 = str.slice(-8, -1);
// Result: 'upon us'
```

### 4. `replace(pattern, replacement)`
Replaces specified value.

```javascript
const str = 'The quick brown fox jumps over the lazy dog.';
const newStr = str.replace('quick', 'fast');
// Result: 'The fast brown fox jumps over the lazy dog.'

// With regex (first occurrence)
const withRegex = str.replace(/brown|lazy/g, 'red');
// Result: 'The quick red fox jumps over the red dog.'

// With function as replacer
const capitalized = str.replace(/\b\w+\b/g, function(word) {
  return word.charAt(0).toUpperCase() + word.slice(1);
});
// Result: 'The Quick Brown Fox Jumps Over The Lazy Dog.'
```

### 5. `replaceAll(pattern, replacement)`
Replaces all occurrences of specified value.

```javascript
const str = 'The quick brown fox jumps over the lazy dog. The dog is lazy.';
const newStr = str.replaceAll('lazy', 'active');
// Result: 'The quick brown fox jumps over the active dog. The dog is active.'

// With regex
const newStrRegex = str.replaceAll(/dog/g, 'cat');
// Result: 'The quick brown fox jumps over the lazy cat. The cat is lazy.'
```

### 6. `toLowerCase()` / `toUpperCase()`
Converts to lower/upper case.

```javascript
const sentence = 'The Quick Brown Fox';
const lower = sentence.toLowerCase();
// Result: 'the quick brown fox'

const upper = sentence.toUpperCase();
// Result: 'THE QUICK BROWN FOX'
```

### 7. `trim()` / `trimStart()` / `trimEnd()`
Removes whitespace.

```javascript
const greeting = '   Hello world!   ';
const trimmed = greeting.trim();
// Result: 'Hello world!'

const trimmedStart = greeting.trimStart();
// Result: 'Hello world!   '

const trimmedEnd = greeting.trimEnd();
// Result: '   Hello world!'
```

### 8. `startsWith(searchString, position)` / `endsWith(searchString, length)`
Checks if string starts/ends with value.

```javascript
const str = 'To be, or not to be, that is the question.';

// startsWith
const startsWithTo = str.startsWith('To be');
// Result: true

// With position parameter (start checking from position)
const startsWithOr = str.startsWith('or', 7);
// Result: true

// endsWith
const endsWithQuestion = str.endsWith('question.');
// Result: true

// With length parameter (consider only first n characters)
const endsWithBe = str.endsWith('be', 9);
// Result: true (considers only 'To be, or')
```

## Map Methods

### 1. `new Map([iterable])`
Creates a new Map object.

```javascript
// Empty Map
const emptyMap = new Map();

// From array of key-value pairs
const map1 = new Map([
  ['key1', 'value1'],
  ['key2', 'value2']
]);

// From another Map
const map2 = new Map(map1);
```

### 2. `map.set(key, value)`
Adds or updates an element with key and value.

```javascript
const contacts = new Map();
contacts.set('Jessie', {phone: '213-555-1234', address: '123 N 1st Ave'});
contacts.set('Hilary', {phone: '617-555-4321', address: '321 S 2nd St'});

// Chaining sets
contacts
  .set('Alice', {phone: '415-555-8765', address: '456 W 3rd Ave'})
  .set('Bob', {phone: '510-555-9876', address: '789 E 4th Blvd'});
```

### 3. `map.get(key)`
Returns value associated with key, or undefined.

```javascript
const contacts = new Map([
  ['Jessie', {phone: '213-555-1234', address: '123 N 1st Ave'}],
  ['Hilary', {phone: '617-555-4321', address: '321 S 2nd St'}]
]);

const jessieContact = contacts.get('Jessie');
// Result: {phone: '213-555-1234', address: '123 N 1st Ave'}

const nonExistentContact = contacts.get('John');
// Result: undefined
```

### 4. `map.has(key)`
Returns boolean indicating if key exists.

```javascript
const contacts = new Map([
  ['Jessie', {phone: '213-555-1234', address: '123 N 1st Ave'}]
]);

const hasJessie = contacts.has('Jessie');
// Result: true

const hasBob = contacts.has('Bob');
// Result: false
```

### 5. `map.delete(key)`
Removes key-value pair and returns success.

```javascript
const contacts = new Map([
  ['Jessie', {phone: '213-555-1234', address: '123 N 1st Ave'}],
  ['Hilary', {phone: '617-555-4321', address: '321 S 2nd St'}]
]);

const wasDeleted = contacts.delete('Jessie');
// Result: true (deleted successfully)

const wasNonExistentDeleted = contacts.delete('Bob');
// Result: false (key didn't exist)
```

### 6. `map.clear()`
Removes all key-value pairs.

```javascript
const contacts = new Map([
  ['Jessie', {phone: '213-555-1234', address: '123 N 1st Ave'}],
  ['Hilary', {phone: '617-555-4321', address: '321 S 2nd St'}]
]);

contacts.clear();
// Map is now empty
console.log(contacts.size);
// Result: 0
```

### 7. `map.size`
Returns number of key-value pairs.

```javascript
const contacts = new Map([
  ['Jessie', {phone: '213-555-1234', address: '123 N 1st Ave'}],
  ['Hilary', {phone: '617-555-4321', address: '321 S 2nd St'}]
]);

console.log(contacts.size);
// Result: 2
```

### 8. `map.keys()` / `map.values()` / `map.entries()`
Returns iterators for keys/values/entries.

```javascript
const contacts = new Map([
  ['Jessie', {phone: '213-555-1234', address: '123 N 1st Ave'}],
  ['Hilary', {phone: '617-555-4321', address: '321 S 2nd St'}]
]);

// Iterate through keys
for (const key of contacts.keys()) {
  console.log(key);
}
// Output:
// Jessie
// Hilary

// Iterate through values
for (const value of contacts.values()) {
  console.log(value);
}
// Output:
// {phone: '213-555-1234', address: '123 N 1st Ave'}
// {phone: '617-555-4321', address: '321 S 2nd St'}

// Iterate through entries
for (const [key, value] of contacts.entries()) {
  console.log(`${key}: ${value.phone}`);
}
// Output:
// Jessie: 213-555-1234
// Hilary: 617-555-4321
```

### 9. `map.forEach(callback(value, key, map), thisArg)`
Executes callback for each key-value pair.

```javascript
const contacts = new Map([
  ['Jessie', {phone: '213-555-1234', address: '123 N 1st Ave'}],
  ['Hilary', {phone: '617-555-4321', address: '321 S 2nd St'}]
]);

// Basic usage
contacts.forEach((value, key) => {
  console.log(`${key}: ${value.phone}`);
});
// Output:
// Jessie: 213-555-1234
// Hilary: 617-555-4321

// With thisArg
const logger = {
  prefix: 'Contact',
  log: function(map) {
    map.forEach(function(value, key) {
      console.log(`${this.prefix} ${key}: ${value.phone}`);
    }, this);
  }
};
logger.log(contacts);
// Output:
// Contact Jessie: 213-555-1234
// Contact Hilary: 617-555-4321
```

## Object Methods

### 1. `Object.keys(obj)`
Returns array of object's own enumerable property names.

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30
};

const keys = Object.keys(person);
// Result: ['firstName', 'lastName', 'age']

// With array-like object
const arrayLike = { 0: 'a', 1: 'b', 2: 'c', length: 3 };
const keysArrayLike = Object.keys(arrayLike);
// Result: ['0', '1', '2', 'length']
```

### 2. `Object.values(obj)`
Returns array of object's own enumerable property values.

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30
};

const values = Object.values(person);
// Result: ['John', 'Doe', 30]

// With array-like object
const arrayLike = { 0: 'a', 1: 'b', 2: 'c', length: 3 };
const valuesArrayLike = Object.values(arrayLike);
// Result: ['a', 'b', 'c', 3]
```

### 3. `Object.entries(obj)`
Returns array of object's own enumerable [key, value] pairs.

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe',
  age: 30
};

const entries = Object.entries(person);
// Result: [['firstName', 'John'], ['lastName', 'Doe'], ['age', 30]]

// Convert back to object
const backToObject = Object.fromEntries(entries);
// Result: {firstName: 'John', lastName: 'Doe', age: 30}
```

### 4. `Object.assign(target, ...sources)`
Copies properties from source objects to target object.

```javascript
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };

const result = Object.assign(target, source);
// target is now { a: 1, b: 4, c: 5 }
// result === target

// Clone an object
const clone = Object.assign({}, target);
// clone is { a: 1, b: 4, c: 5 }

// Merge multiple objects
const merged = Object.assign({}, { x: 1 }, { y: 2 }, { z: 3 });
// Result: { x: 1, y: 2, z: 3 }
```

### 5. `Object.hasOwnProperty(prop)`
Checks if property belongs directly to object.

```javascript
const person = {
  name: 'John',
  age: 30
};

console.log(person.hasOwnProperty('name'));
// Result: true

console.log(person.hasOwnProperty('toString'));
// Result: false (inherited from prototype)

// Safer way using call (in case hasOwnProperty is overridden)
console.log(Object.prototype.hasOwnProperty.call(person, 'name'));
// Result: true
```

### C. `Object.freeze(obj)` / `Object.seal(obj)`
Makes object immutable / prevents adding new properties.

```javascript
const person = {
  name: 'John',
  address: {
    city: 'New York'
  }
};

// Freeze
Object.freeze(person);
person.name = 'Jane'; // No effect in strict mode
person.age = 31; // No effect in strict mode
console.log(person);
// Still {name: 'John', address: {city: 'New York'}}

// Note: freeze is shallow
person.address.city = 'Boston'; // Works!
console.log(person.address.city);
// Result: 'Boston'

// Seal
const car = { make: 'Toyota', model: 'Corolla' };
Object.seal(car);
car.make = 'Honda'; // Works
car.year = 2020; // No effect in strict mode
delete car.model; // No effect in strict mode
console.log(car);
// Result: {make: 'Honda', model: 'Corolla'}
```

### 7. `JSON.stringify(value, replacer, space)` / `JSON.parse(text, reviver)`
Converts to/from JSON.

```javascript
const person = {
  name: 'John',
  age: 30,
  isEmployed: true,
  birth: new Date('1990-01-01'),
  greet: function() { return `Hello, I'm ${this.name}`; } // Will be excluded
};

// Basic usage
const json = JSON.stringify(person);
// Result: '{"name":"John","age":30,"isEmployed":true,"birth":"1990-01-01T00:00:00.000Z"}'

// With replacer function
const jsonFiltered = JSON.stringify(person, (key, value) => {
  if (key === 'age') return undefined; // Skip age
  if (key === 'birth') return value.toISOString().split('T')[0]; // Format date
  return value;
});
// Result: '{"name":"John","isEmployed":true,"birth":"1990-01-01"}'

// With replacer array
const jsonSelectedProps = JSON.stringify(person, ['name', 'isEmployed']);
// Result: '{"name":"John","isEmployed":true}'

// With space for pretty printing
const jsonPretty = JSON.stringify(person, null, 2);
// Result:
// {
//   "name": "John",
//   "age": 30,
//   "isEmployed": true,
//   "birth": "1990-01-01T00:00:00.000Z"
// }

// Parse JSON
const parsed = JSON.parse(json);
// Result: {name: 'John', age: 30, isEmployed: true, birth: '1990-01-01T00:00:00.000Z'}

// Parse with reviver to handle dates
const parsedWithDates = JSON.parse(json, (key, value) => {
  if (key === 'birth') return new Date(value);
  return value;
});
// parsedWithDates.birth is now a Date object
```
