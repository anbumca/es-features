# JavaScript Arrays - Complete Interview & Development Guide
- Introduction

Arrays are one of the most fundamental and frequently used data structures in JavaScript. They allow you to store multiple values in a single variable and provide powerful built-in methods for:

Data Storage
- Iteration
- Searching
- Filtering
- Transformation
- Aggregation
- Sorting
Data Manipulation
📑 Table of Contents
- Fundamentals
Array Declaration
Accessing Elements
Array Length
Modification Methods
- push()
- pop()
- shift()
- unshift()
- splice()
Extraction Methods
- slice()
Iteration Methods
- forEach()
- Transformation Methods
- map()
- filter()
- reduce()
- flat()
- flatMap()
Search Methods
- find()
- findIndex()
- includes()
- indexOf()
Utility Methods
- concat()
- join()
- reverse()
- sort()
ES6+ Array Features
Spread Operator (...)
Array Destructuring
- Array.from()
- Array.of()
- Array.isArray()
Interview Questions
Remove Duplicates
Group By
🎯 Fundamentals
- Array Declaration
- Purpose

Store multiple values in a single variable.

```
const fruits = ["Apple", "Banana", "Orange"];
```

## 2. Accessing Elements
- Purpose

Access values using indexes.

```
const fruits = ["Apple", "Banana", "Orange"];
```

console.log(fruits[0]);
console.log(fruits[1]);

- Output
- Apple
- Banana

## 3. Array Length
- Purpose

Get the number of elements.

```
const fruits = ["Apple", "Banana", "Orange"];
```

console.log(fruits.length);

- Output
- 3

🔧 Modification Methods
Method	Descriptionpush()	Add to end
pop()	Remove from end
shift()	Remove from beginning
unshift()	Add to beginning
splice()	Add/Remove/Replace
- push()
```
const arr = [1, 2, 3];
```

arr.push(4);

console.log(arr);

- Output
[1, 2, 3, 4]

## 5. pop()
```
const arr = [1, 2, 3];
```

arr.pop();

console.log(arr);

- Output
[1, 2]

## 6. shift()
```
const arr = [1, 2, 3];
```

arr.shift();

console.log(arr);

- Output
[2, 3]

## 7. unshift()
```
const arr = [2, 3];
```

arr.unshift(1);

console.log(arr);

- Output
[1, 2, 3]

## 8. splice()
Remove Elements
```
const arr = [1, 2, 3, 4];
```

arr.splice(1, 2);

console.log(arr);

- Output
[1, 4]

Add Elements
```
const arr = [1, 4];
```

arr.splice(1, 0, 2, 3);

console.log(arr);

- Output
[1, 2, 3, 4]

🔄 Iteration & Transformation Methods
Method	Returns New Array	PurposeforEach()	❌	Iterate
map()	✅	Transform
filter()	✅	Filter
reduce()	❌	Accumulate
flat()	✅	Flatten
flatMap()	✅	Map + Flatten
- forEach()
```
const arr = [1, 2, 3];
```

arr.forEach(item => {
```
console.log(item);
```
});

## 10. map()
```
const numbers = [1, 2, 3];
```

```
const doubled = numbers.map(
num => num * 2
```
);

console.log(doubled);

- Output
[2, 4, 6]

## 11. filter()
```
const numbers = [1, 2, 3, 4, 5];
```

```
const even = numbers.filter(
num => num % 2 === 0
```
);

console.log(even);

- Output
[2, 4]

## 12. reduce()
```
const numbers = [1, 2, 3, 4];
```

```
const sum = numbers.reduce(
(total, num) => total + num,
```
- 0
);

console.log(sum);

- Output
- 10

🔍 Search Methods
Method	Return Typefind()	Element
findIndex()	Index
includes()	Boolean
indexOf()	Index
- find()
```
const users = [
{ id: 1, name: "John" },
{ id: 2, name: "Mike" }
```
];

```
const user = users.find(
u => u.id === 2
```
);

console.log(user);

## 14. findIndex()
```
const nums = [10, 20, 30];
```

- console.log(
```
nums.findIndex(n => n === 20)
```
);

- Output
- 1

🚀 ES6+ Array Features
Spread Operator (...)
```
const arr1 = [1, 2];
const arr2 = [3, 4];
```

```
const merged = [
```
...arr1,
- ...arr2
];

console.log(merged);

Array Destructuring
```
const arr = [10, 20, 30];
```

```
const [a, b, c] = arr;
```

console.log(a, b, c);

- Array.from()
```
const str = "HELLO";
```

```
const arr = Array.from(str);
```

console.log(arr);

- Output
[**H**, **E**, **L**, **L**, **O**]

- Array.of()
```
const arr = Array.of(1, 2, 3);
```

console.log(arr);

- Array.isArray()
console.log(Array.isArray([1, 2, 3]));

console.log(Array.isArray(**Hello**));

- Output
- true
- false

💼 Most Asked Interview Questions
Remove Duplicates
```
const nums = [1, 2, 2, 3, 3, 4];
```

```
const unique = [...new Set(nums)];
```

console.log(unique);

- Output
[1, 2, 3, 4]

Group By Property
```
const users = [
{ name: "John", dept: "IT" },
{ name: "Mike", dept: "HR" },
{ name: "David", dept: "IT" }
```
];

```
const grouped = users.reduce(
(acc, user) => {
acc[user.dept] ??= [];
acc[user.dept].push(user);
return acc;
},
{}
```
);

console.log(grouped);

✅ Top 25 Array Methods for Interviews
- Essential
- push()
- pop()
- shift()
- unshift()
- splice()
- slice()
- map()
- filter()
- reduce()
- find()
- findIndex()
- forEach()
Frequently Asked
- includes()
- indexOf()
- concat()
- join()
- reverse()
- sort()
- flat()
- flatMap()
Modern JavaScript
Spread Operator (...)
Array Destructuring
- Array.from()
- Array.of()
- Array.isArray()
