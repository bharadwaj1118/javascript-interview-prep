# JavaScript Methods Cheat Sheet

## Array Methods

### Basic Array Operations
1. `Array.isArray(obj)` - Checks if an object is an array
2. `Array.from(iterable)` - Creates a new array from an iterable object
3. `Array.of(...items)` - Creates a new array with the given arguments
4. `array.length` - Gets or sets the number of elements in the array
5. `array[index]` - Accesses or sets an element at the specified index

### Adding/Removing Elements
6. `array.push(element1, ..., elementN)` - Adds elements to the end of an array
7. `array.pop()` - Removes and returns the last element
8. `array.unshift(element1, ..., elementN)` - Adds elements to the beginning
9. `array.shift()` - Removes and returns the first element
10. `array.splice(start, deleteCount, item1, ..., itemN)` - Changes array by removing or replacing elements
11. `array.fill(value, start, end)` - Fills array with a static value

### Array Search and Access
12. `array.includes(element, fromIndex)` - Checks if an array contains the element
13. `array.indexOf(element, fromIndex)` - Returns first index of element, or -1
14. `array.lastIndexOf(element, fromIndex)` - Returns last index of element, or -1
15. `array.find(callback)` - Returns first element that satisfies a condition
16. `array.findIndex(callback)` - Returns index of first element that satisfies a condition
17. `array.findLast(callback)` - Returns last element that satisfies a condition
18. `array.findLastIndex(callback)` - Returns index of last element that satisfies a condition

### Array Transformation
19. `array.map(callback)` - Creates new array with results of callback on each element
20. `array.filter(callback)` - Creates new array with elements that pass the test
21. `array.reduce(callback, initialValue)` - Reduces array to a single value (left to right)
22. `array.reduceRight(callback, initialValue)` - Reduces array to a single value (right to left)
23. `array.slice(start, end)` - Returns a shallow copy of a portion of an array
24. `array.flat(depth)` - Creates a new array with all sub-array elements concatenated
25. `array.flatMap(callback)` - Maps each element and flattens the result

### Array Iteration
26. `array.forEach(callback)` - Executes a function once for each array element
27. `array.some(callback)` - Tests if at least one element passes the test
28. `array.every(callback)` - Tests if all elements pass the test
29. `array.entries()` - Returns a new array iterator with key/value pairs
30. `array.keys()` - Returns a new array iterator with keys
31. `array.values()` - Returns a new array iterator with values

### Array Sorting and Reversing
32. `array.sort(compareFunction)` - Sorts the elements of an array in place
33. `array.reverse()` - Reverses the order of elements in an array

### Array to String Conversion
34. `array.join(separator)` - Joins all elements into a string
35. `array.toString()` - Returns a string representing the array
36. `array.toLocaleString()` - Returns a localized string representing the array

### Array Copying and Concatenation
37. `array.concat(array1, ..., arrayN)` - Merges two or more arrays
38. `array.copyWithin(target, start, end)` - Copies a sequence of elements within the array

## Map Methods

### Map Creation and Size
39. `new Map([iterable])` - Creates a new Map object
40. `map.size` - Returns the number of key/value pairs

### Map Modification
41. `map.set(key, value)` - Sets a key-value pair, returns the Map
42. `map.delete(key)` - Removes a key-value pair by key
43. `map.clear()` - Removes all key-value pairs

### Map Access
44. `map.get(key)` - Returns the value associated with key
45. `map.has(key)` - Checks if a key exists

### Map Iteration
46. `map.keys()` - Returns a new iterator with the keys
47. `map.values()` - Returns a new iterator with the values
48. `map.entries()` - Returns a new iterator with [key, value] pairs
49. `map.forEach(callback)` - Executes callback for each key/value pair

## String Methods

### String Creation and Properties
50. `String(value)` - Converts a value to a string
51. `string.length` - Returns the length of a string
52. `string[index]` - Accesses character at specified index (read-only)

### String Search
53. `string.indexOf(searchValue, fromIndex)` - Returns index of first occurrence or -1
54. `string.lastIndexOf(searchValue, fromIndex)` - Returns index of last occurrence or -1
55. `string.includes(searchValue, fromIndex)` - Checks if string contains searchValue
56. `string.startsWith(searchValue, position)` - Checks if string starts with searchValue
57. `string.endsWith(searchValue, length)` - Checks if string ends with searchValue
58. `string.search(regexp)` - Searches for a match between a regexp and a string
59. `string.match(regexp)` - Returns matches against a regular expression
60. `string.matchAll(regexp)` - Returns an iterator of all matches

### String Extraction
61. `string.charAt(index)` - Returns character at specified index
62. `string.charCodeAt(index)` - Returns UTF-16 code at specified index
63. `string.codePointAt(index)` - Returns Unicode code point at specified index
64. `string.slice(start, end)` - Extracts a section of the string
65. `string.substring(start, end)` - Extracts characters between two indices
66. `string.substr(start, length)` - Extracts specified number of characters
67. `string.split(separator, limit)` - Splits string into an array of substrings

### String Transformation
68. `string.toLowerCase()` - Converts string to lowercase
69. `string.toUpperCase()` - Converts string to uppercase
70. `string.toLocaleLowerCase(locale)` - Locale-specific lowercase conversion
71. `string.toLocaleUpperCase(locale)` - Locale-specific uppercase conversion
72. `string.trim()` - Removes whitespace from both ends
73. `string.trimStart()` - Removes whitespace from the beginning
74. `string.trimEnd()` - Removes whitespace from the end
75. `string.padStart(targetLength, padString)` - Pads start with a string
76. `string.padEnd(targetLength, padString)` - Pads end with a string
77. `string.repeat(count)` - Returns a string repeated count times
78. `string.replace(pattern, replacement)` - Replaces first match with replacement
79. `string.replaceAll(pattern, replacement)` - Replaces all matches with replacement
80. `string.concat(string1, ..., stringN)` - Concatenates strings

### String Comparison and Localization
81. `string.localeCompare(compareString, locales, options)` - Compares strings in locale-specific order
82. `string.normalize(form)` - Returns Unicode Normalization Form of the string
83. `string.toLocaleLowerCase(locale)` - Converts to lowercase respecting locale
84. `string.toLocaleUpperCase(locale)` - Converts to uppercase respecting locale

## Object Methods

### Object Creation
85. `Object.create(proto, propertiesObject)` - Creates a new object with the specified prototype
86. `Object.assign(target, ...sources)` - Copies properties from sources to target
87. `Object.fromEntries(iterable)` - Creates an object from key-value pairs

### Object Properties
88. `Object.defineProperty(obj, prop, descriptor)` - Defines a new property directly on an object
89. `Object.defineProperties(obj, props)` - Defines multiple properties
90. `Object.getOwnPropertyDescriptor(obj, prop)` - Returns property descriptor
91. `Object.getOwnPropertyDescriptors(obj)` - Returns all property descriptors
92. `Object.getOwnPropertyNames(obj)` - Returns array of all property names
93. `Object.getOwnPropertySymbols(obj)` - Returns array of all symbol properties
94. `Object.getPrototypeOf(obj)` - Returns the prototype of an object
95. `Object.setPrototypeOf(obj, prototype)` - Sets the prototype of an object

### Object Inspection
96. `Object.keys(obj)` - Returns array of enumerable property names
97. `Object.values(obj)` - Returns array of enumerable property values
98. `Object.entries(obj)` - Returns array of [key, value] pairs
99. `Object.hasOwn(obj, prop)` - Checks if property exists as direct property
100. `object.hasOwnProperty(prop)` - Checks if property exists as direct property
101. `object.propertyIsEnumerable(prop)` - Checks if property is enumerable
102. `object.isPrototypeOf(obj)` - Checks if object exists in another object's prototype chain

### Object Protection
103. `Object.freeze(obj)` - Freezes an object (prevents modification)
104. `Object.seal(obj)` - Seals an object (prevents adding/deleting properties)
105. `Object.preventExtensions(obj)` - Prevents adding new properties
106. `Object.isFrozen(obj)` - Checks if an object is frozen
107. `Object.isSealed(obj)` - Checks if an object is sealed
108. `Object.isExtensible(obj)` - Checks if an object is extensible

### Object Conversion
109. `object.toString()` - Returns string representation of the object
110. `object.toLocaleString()` - Returns localized string representation
111. `object.valueOf()` - Returns primitive value of the object

## Additional Useful Methods

### Array Methods (Additional)
112. `array.at(index)` - Returns element at index (supports negative indexing)
113. `array.with(index, value)` - Returns a new array with the element at index replaced with value
114. `array.toReversed()` - Returns a new array with elements in reversed order
115. `array.toSorted(compareFn)` - Returns a new sorted array
116. `array.toSpliced(start, deleteCount, ...items)` - Returns a new array with spliced elements

### String Methods (Additional)
117. `string.at(index)` - Returns character at index (supports negative indexing)
118. `string.replaceAll(searchValue, replacement)` - Replaces all occurrences
119. `string.trimStart()` / `string.trimLeft()` - Trims start of string
120. `string.trimEnd()` / `string.trimRight()` - Trims end of string

### Object Methods (Advanced)
121. `Reflect.ownKeys(obj)` - Returns all own property keys (string and symbol)
122. `Object.is(value1, value2)` - Determines if two values are the same value

### Set Methods
123. `new Set([iterable])` - Creates a new Set object
124. `set.size` - Returns the number of elements
125. `set.add(value)` - Adds a new element
126. `set.delete(value)` - Removes an element
127. `set.has(value)` - Checks if a value exists
128. `set.clear()` - Removes all elements
129. `set.forEach(callback)` - Executes callback for each value
130. `set.values()` - Returns a new iterator with the values
131. `set.keys()` - Same as values() for compatibility with Map
132. `set.entries()` - Returns a new iterator with [value, value] pairs

### WeakMap and WeakSet
133. `new WeakMap([iterable])` - Creates a WeakMap (keys must be objects)
134. `weakMap.set(key, value)` - Sets a key-value pair
135. `weakMap.get(key)` - Gets the value for a key
136. `weakMap.has(key)` - Checks if a key exists
137. `weakMap.delete(key)` - Removes a key-value pair
138. `new WeakSet([iterable])` - Creates a WeakSet (values must be objects)
139. `weakSet.add(value)` - Adds a value
140. `weakSet.has(value)` - Checks if a value exists
141. `weakSet.delete(value)` - Removes a value

### JSON Methods
142. `JSON.parse(text)` - Parses JSON string into an object
143. `JSON.stringify(value, replacer, space)` - Converts object to JSON string

### TypedArray Methods
144. `new TypedArray(length)` - Creates a new typed array with specified length
145. `typedArray.set(array, offset)` - Stores multiple values in the typed array
146. `typedArray.subarray(begin, end)` - Returns a new typed array from begin to end

### Promise Methods
147. `Promise.all(iterable)` - Waits for all promises to be resolved
148. `Promise.allSettled(iterable)` - Waits for all promises to be settled
149. `Promise.race(iterable)` - Waits for first promise to be settled
150. `Promise.any(iterable)` - Waits for first promise to be fulfilled
