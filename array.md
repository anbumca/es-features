Below are the most important JavaScript Array concepts with explanations and examples.

1. Array Declaration
Explanation

Arrays store multiple values in a single variable.

const fruits = ["Apple", "Banana", "Orange"];

console.log(fruits);

2. Accessing Elements
Explanation

Array elements are accessed using their index. Index starts from 0.

const fruits = ["Apple", "Banana", "Orange"];

console.log(fruits[0]); // Apple
console.log(fruits[1]); // Banana

3. Array Length
Explanation

Returns the number of elements.

const fruits = ["Apple", "Banana", "Orange"];

console.log(fruits.length); // 3

4. push()
Explanation

Adds element(s) at the end.

const arr = [1, 2, 3];

arr.push(4);

console.log(arr); // [1,2,3,4]

5. pop()
Explanation

Removes the last element.

const arr = [1, 2, 3];

arr.pop();

console.log(arr); // [1,2]

6. shift()
Explanation

Removes the first element.

const arr = [1, 2, 3];

arr.shift();

console.log(arr); // [2,3]

7. unshift()
Explanation

Adds element(s) at the beginning.

const arr = [2, 3];

arr.unshift(1);

console.log(arr); // [1,2,3]

8. splice()
Explanation

Add, remove, or replace elements.

const arr = [1, 2, 3, 4];

arr.splice(1, 2);

console.log(arr); // [1,4]


Add elements:

const arr = [1, 4];

arr.splice(1, 0, 2, 3);

console.log(arr); // [1,2,3,4]

9. slice()
Explanation

Returns a portion of an array.

const arr = [1, 2, 3, 4, 5];

const result = arr.slice(1, 4);

console.log(result); // [2,3,4]

10. forEach()
Explanation

Executes a function for each element.

const arr = [1, 2, 3];

arr.forEach(num => {
    console.log(num);
});

11. map()
Explanation

Creates a new array by transforming elements.

const numbers = [1, 2, 3];

const doubled = numbers.map(num => num * 2);

console.log(doubled);
// [2,4,6]

12. filter()
Explanation

Returns elements matching a condition.

const numbers = [1, 2, 3, 4, 5];

const even = numbers.filter(num => num % 2 === 0);

console.log(even);
// [2,4]

13. reduce()
Explanation

Reduces array into a single value.

const numbers = [1, 2, 3, 4];

const sum = numbers.reduce((total, num) => total + num, 0);

console.log(sum);
// 10

14. find()
Explanation

Returns first matching element.

const users = [
    {id: 1, name: "John"},
    {id: 2, name: "Mike"}
];

const user = users.find(u => u.id === 2);

console.log(user);

15. findIndex()
Explanation

Returns index of matching element.

const nums = [10, 20, 30];

const index = nums.findIndex(num => num === 20);

console.log(index); // 1

16. includes()
Explanation

Checks if value exists.

const colors = ["red", "blue"];

console.log(colors.includes("red")); // true

17. indexOf()
Explanation

Returns position of element.

const colors = ["red", "blue", "green"];

console.log(colors.indexOf("green")); // 2

18. concat()
Explanation

Combines arrays.

const a = [1, 2];
const b = [3, 4];

const result = a.concat(b);

console.log(result);
// [1,2,3,4]

19. join()
Explanation

Converts array to string.

const arr = ["JavaScript", "Array"];

console.log(arr.join(" - "));

// JavaScript - Array

20. reverse()
Explanation

Reverses elements.

const arr = [1, 2, 3];

arr.reverse();

console.log(arr);
// [3,2,1]

21. sort()
Explanation

Sorts elements.

const arr = [5, 2, 8, 1];

arr.sort((a, b) => a - b);

console.log(arr);
// [1,2,5,8]

22. flat()
Explanation

Flattens nested arrays.

const arr = [1, [2, 3], [4, 5]];

console.log(arr.flat());

// [1,2,3,4,5]

23. flatMap()
Explanation

Map + Flat in one step.

const arr = ["hello world", "javascript array"];

const result = arr.flatMap(item => item.split(" "));

console.log(result);

24. Spread Operator (...)
Explanation

Copy or merge arrays.

const arr1 = [1, 2];
const arr2 = [3, 4];

const merged = [...arr1, ...arr2];

console.log(merged);

25. Array Destructuring
Explanation

Extract values from arrays.

const arr = [10, 20, 30];

const [a, b, c] = arr;

console.log(a);
console.log(b);
console.log(c);

26. Array.from()
Explanation

Creates an array from iterable objects.

const str = "HELLO";

const arr = Array.from(str);

console.log(arr);

// ["H","E","L","L","O"]

27. Array.of()
Explanation

Creates array from values.

const arr = Array.of(1, 2, 3);

console.log(arr);

// [1,2,3]

28. Array.isArray()
Explanation

Checks whether a value is an array.

console.log(Array.isArray([1,2,3]));
// true

console.log(Array.isArray("Hello"));
// false

29. Remove Duplicates (Interview)
const nums = [1, 2, 2, 3, 3, 4];

const unique = [...new Set(nums)];

console.log(unique);

// [1,2,3,4]

30. Group By (Interview)
const users = [
    {name: "John", dept: "IT"},
    {name: "Mike", dept: "HR"},
    {name: "David", dept: "IT"}
];

const result = users.reduce((acc, user) => {
    acc[user.dept] = acc[user.dept] || [];
    acc[user.dept].push(user);
    return acc;
}, {});

console.log(result);

Most Important Array Methods for Interviews

✅ push()
 ✅ pop()
 ✅ shift()
 ✅ unshift()
 ✅ splice()
 ✅ slice()
 ✅ map()
 ✅ filter()
 ✅ reduce()
 ✅ find()
 ✅ findIndex()
 ✅ forEach()
 ✅ sort()
 ✅ reverse()
 ✅ flat()
 ✅ flatMap()
 ✅ concat()
 ✅ join()
 ✅ includes()
 ✅ indexOf()
 ✅ Array.from()
 ✅ Array.of()
 ✅ Array.isArray()
 ✅ Spread Operator
 ✅ Destructuring
 ✅ Remove Duplicates using Set

Master these concepts and you'll cover about 90% of JavaScript array questions asked in interviews and real-world development.
