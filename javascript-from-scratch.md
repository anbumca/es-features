# JavaScript From Scratch — A Fresher's Guide

A beginner-friendly guide to learning JavaScript from zero. Each section explains
the "why", shows runnable example code, and ends with small exercises. Work through
it top to bottom. Type every example yourself — don't just read.

---

## Table of Contents

1. [What is JavaScript?](#1-what-is-javascript)
2. [Setup — Running Your First Code](#2-setup--running-your-first-code)
3. [Variables](#3-variables)
4. [Data Types](#4-data-types)
5. [Operators](#5-operators)
6. [Input and Output](#6-input-and-output)
7. [Control Flow — Conditions](#7-control-flow--conditions)
8. [Loops](#8-loops)
9. [Functions](#9-functions)
10. [Arrays](#10-arrays)
11. [Objects](#11-objects)
12. [Strings](#12-strings)
13. [The DOM — Making Web Pages Interactive](#13-the-dom--making-web-pages-interactive)
14. [Events](#14-events)
15. [Error Handling](#15-error-handling)
16. [Capstone Project — To-Do List](#16-capstone-project--to-do-list)
17. [Async JavaScript — Promises, async/await, fetch](#17-async-javascript--promises-asyncawait-fetch)
18. [AI in JavaScript — Your First AI Feature](#18-ai-in-javascript--your-first-ai-feature)

**More Essentials** (read these alongside Sections 3–9 — they fill in common gaps):

19. [Truthy & Falsy Values](#19-truthy--falsy-values)
20. [Destructuring & Spread/Rest](#20-destructuring--spreadrest)
21. [Working with JSON](#21-working-with-json)
22. [Debugging & Reading Errors](#22-debugging--reading-errors)
23. [Object-Oriented Programming (OOP) with Classes](#23-object-oriented-programming-oop-with-classes)

> **A note on ES versions:** This guide teaches **modern JavaScript (ES6 / ES2015 and
> later)**, which is the standard today. Features are labeled where helpful: **(ES5)**
> for older syntax that still works everywhere, **(ES6+)** for modern additions. For
> freshers, always prefer the modern style — it's cleaner and what real codebases use.

---

## 1. What is JavaScript?

JavaScript (JS) is the programming language of the web. It runs inside every web
browser and lets web pages *do things*: respond to clicks, update content without
reloading, validate forms, animate, and talk to servers.

- **HTML** = the structure of a page (the content).
- **CSS** = the styling (how it looks).
- **JavaScript** = the behavior (what it does).

JavaScript also runs *outside* the browser using **Node.js**, which lets you build
servers, tools, and scripts. For this guide we start in the browser because you see
results instantly.

---

## 2. Setup — Running Your First Code

You don't need to install anything to start. Every browser has a built-in
**Console** where you can run JavaScript.

### Option A — The browser console (fastest)

1. Open any web page (or a blank tab).
2. Press `F12` (or right-click → **Inspect**).
3. Click the **Console** tab.
4. Type this and press Enter:

```js
console.log("Hello, world!");
```

`console.log(...)` prints a value to the console. It's your main tool for seeing
what your code is doing.

### Option B — An HTML file (closer to real projects)

Create a file called `index.html`:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My First JS</title>
  </head>
  <body>
    <h1>Open the console to see output</h1>

    <script>
      console.log("Hello from a file!");
    </script>
  </body>
</html>
```

Open the file in a browser and check the console. The `<script>` tag is where your
JavaScript lives.

> **Tip:** Keep the console open while you learn. You'll live there.

### Exercise 2

1. Print your name to the console.
2. Print the result of `console.log("JS" + " is fun")` and notice what `+` did.

---

## 3. Variables

A **variable** is a named box that stores a value so you can reuse it.

```js
let age = 25;
const name = "Asha";
```

- `let` — a variable whose value **can change** later.
- `const` — a **constant**; its value **cannot be reassigned**.
- `var` — the old way. Avoid it in new code; prefer `let` and `const`.

```js
let score = 10;
score = 20;        // OK, let can change
console.log(score); // 20

const pi = 3.14;
// pi = 3.15;       // Error! const cannot be reassigned
```

**Rule of thumb:** use `const` by default. Switch to `let` only when you know the
value needs to change. This prevents accidental changes.

### Naming rules

- Use letters, digits, `_`, `$`. Cannot start with a digit.
- Use `camelCase`: `firstName`, `totalPrice`, `isLoggedIn`.
- Names should describe the value: `userAge` is better than `x`.

### Exercise 3

1. Create a `const` for your city and a `let` for your current mood.
2. Change the mood variable and print both.

---

## 4. Data Types

A **data type** is the kind of value a variable holds. JavaScript has a few core types.

### Primitive types

```js
let text = "Hello";        // String  — text, in quotes
let count = 42;            // Number  — integers and decimals
let price = 9.99;          // Number  — no separate "float" type
let isReady = true;        // Boolean — true or false
let nothing = null;        // Null    — intentional "no value"
let notSet;                // Undefined — declared but no value yet
```

### Checking a type

Use `typeof` to see what type a value is:

```js
console.log(typeof "hi");    // "string"
console.log(typeof 10);      // "number"
console.log(typeof true);    // "boolean"
console.log(typeof notSet);  // "undefined"
```

### Strings can use single or double quotes

```js
let a = "double";
let b = 'single';
let c = `backticks`; // template literal — allows embedding values
```

Template literals (backticks) let you insert values with `${...}`:

```js
let name = "Asha";
let greeting = `Hello, ${name}!`;
console.log(greeting); // Hello, Asha!
```

### Converting between types

```js
let numText = "123";
let num = Number(numText);   // string -> number: 123
let backToText = String(num); // number -> string: "123"
let truthy = Boolean(1);      // -> true
```

### Exercise 4

1. Create one variable of each type: string, number, boolean.
2. Use `typeof` to print each one's type.
3. Convert the string `"50"` to a number and add 10 to it.

---

## 5. Operators

Operators let you compute and compare.

### Arithmetic

```js
console.log(5 + 2);  // 7   addition
console.log(5 - 2);  // 3   subtraction
console.log(5 * 2);  // 10  multiplication
console.log(5 / 2);  // 2.5 division
console.log(5 % 2);  // 1   remainder (modulo)
console.log(5 ** 2); // 25  exponent (5 to the power 2)
```

### Assignment

```js
let x = 10;
x += 5; // same as x = x + 5  -> 15
x -= 3; // 12
x *= 2; // 24
```

### Comparison (returns a boolean)

```js
console.log(5 > 3);    // true
console.log(5 < 3);    // false
console.log(5 >= 5);   // true
console.log(5 === 5);  // true  (strict equal: value AND type)
console.log(5 === "5"); // false (number vs string)
console.log(5 == "5");  // true  (loose equal: converts types — avoid)
```

> **Important:** Always use `===` and `!==` (strict). Avoid `==` and `!=` because
> they do surprising type conversions.

### Logical

```js
console.log(true && false); // false — AND (both must be true)
console.log(true || false); // true  — OR  (at least one true)
console.log(!true);         // false — NOT (flips it)
```

### Exercise 5

1. Check whether a number is even using `%`.
2. Write a comparison that is `true` only when a person's age is between 18 and 60.

---

## 6. Input and Output

### Output

- `console.log(...)` — print to the console (for debugging/learning).
- `alert(...)` — pop up a message box in the browser.
- `document.write(...)` — write directly to the page (rarely used in real apps).

### Input

- `prompt(...)` — ask the user for text in the browser.

```js
let name = prompt("What is your name?");
console.log("Hello, " + name);
```

`prompt` always returns a **string**. Convert it if you need a number:

```js
let age = Number(prompt("Your age?"));
console.log(age + 1);
```

### Exercise 6

1. Ask the user for two numbers and print their sum.
2. Remember to convert the inputs to numbers first — try it without converting and
   see what `"2" + "3"` gives you.

---

## 7. Control Flow — Conditions

Programs make decisions. `if` runs code only when a condition is true.

```js
let age = 20;

if (age >= 18) {
  console.log("You are an adult.");
}
```

### if / else

```js
let age = 15;

if (age >= 18) {
  console.log("Adult");
} else {
  console.log("Minor");
}
```

### else if — multiple paths

```js
let score = 75;

if (score >= 90) {
  console.log("Grade A");
} else if (score >= 75) {
  console.log("Grade B");
} else if (score >= 50) {
  console.log("Grade C");
} else {
  console.log("Fail");
}
```

The first condition that is `true` wins; the rest are skipped.

### switch — comparing one value against many options

```js
let day = "Mon";

switch (day) {
  case "Sat":
  case "Sun":
    console.log("Weekend");
    break;
  default:
    console.log("Weekday");
}
```

`break` stops the switch; without it, execution "falls through" to the next case.

### Ternary — a short if/else that returns a value

```js
let age = 20;
let type = age >= 18 ? "Adult" : "Minor";
console.log(type); // Adult
```

### Exercise 7

1. Ask for a number and print whether it is positive, negative, or zero.
2. Convert a score (0–100) into a letter grade using `if / else if`.

---

## 8. Loops

Loops repeat work so you don't copy-paste code.

### for — when you know how many times

```js
for (let i = 1; i <= 5; i++) {
  console.log("Count:", i);
}
// Count: 1 ... Count: 5
```

The three parts: **start** (`let i = 1`), **condition** (`i <= 5`), **step** (`i++`).

### while — repeat while a condition is true

```js
let i = 1;
while (i <= 5) {
  console.log(i);
  i++; // don't forget this, or it loops forever!
}
```

### do...while — runs at least once

```js
let n = 10;
do {
  console.log(n);
  n++;
} while (n < 5); // runs once even though 10 < 5 is false
```

### Looping over a list

```js
let fruits = ["apple", "banana", "cherry"];

for (let fruit of fruits) {
  console.log(fruit);
}
```

### break and continue

```js
for (let i = 1; i <= 10; i++) {
  if (i === 5) break;    // stop the loop entirely
  if (i % 2 === 0) continue; // skip this iteration
  console.log(i); // 1, 3
}
```

### Exercise 8

1. Print numbers 1 to 10 using a `for` loop.
2. Print only even numbers from 1 to 20.
3. Sum all numbers from 1 to 100 and print the total.

---

## 9. Functions

A **function** is a reusable block of code. Define it once, call it many times.

```js
function greet() {
  console.log("Hello!");
}

greet(); // call it
greet(); // call again
```

### Parameters and arguments

Functions can take inputs (**parameters**):

```js
function greet(name) {
  console.log("Hello, " + name);
}

greet("Asha"); // "Asha" is the argument
greet("Ravi");
```

### Return values

Functions can send a value back with `return`:

```js
function add(a, b) {
  return a + b;
}

let sum = add(3, 4);
console.log(sum); // 7
```

Once `return` runs, the function stops.

### Arrow functions (modern shorthand)

```js
const add = (a, b) => a + b;
const square = (x) => x * x;
const sayHi = () => console.log("Hi");

console.log(add(2, 3)); // 5
console.log(square(4)); // 16
```

Arrow functions are a shorter way to write functions. For a single expression, the
value is returned automatically (no `return` keyword needed).

### Default parameters

```js
function greet(name = "friend") {
  console.log("Hello, " + name);
}

greet();        // Hello, friend
greet("Asha");  // Hello, Asha
```

### Exercise 9

1. Write a function `isEven(n)` that returns `true` if `n` is even.
2. Write a function `max(a, b)` that returns the larger of two numbers.
3. Write a function that takes a name and returns a greeting string (not just prints it).

---

## 10. Arrays

An **array** is an ordered list of values stored in one variable.

```js
let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // "apple"  (index starts at 0)
console.log(fruits[2]); // "cherry"
console.log(fruits.length); // 3
```

### Changing arrays

```js
let nums = [1, 2, 3];

nums.push(4);     // add to end        -> [1, 2, 3, 4]
nums.pop();       // remove from end   -> [1, 2, 3]
nums.unshift(0);  // add to start      -> [0, 1, 2, 3]
nums.shift();     // remove from start -> [1, 2, 3]

nums[0] = 10;     // change by index   -> [10, 2, 3]
```

### Looping over an array

```js
let colors = ["red", "green", "blue"];

for (let color of colors) {
  console.log(color);
}

// With index:
colors.forEach((color, index) => {
  console.log(index, color);
});
```

### Useful array methods

```js
let nums = [1, 2, 3, 4, 5];

// map: transform every item -> new array
let doubled = nums.map((n) => n * 2);     // [2, 4, 6, 8, 10]

// filter: keep items that pass a test
let evens = nums.filter((n) => n % 2 === 0); // [2, 4]

// reduce: combine into one value
let total = nums.reduce((sum, n) => sum + n, 0); // 15

// find: first item that matches
let firstBig = nums.find((n) => n > 3); // 4

// includes: does it contain a value?
console.log(nums.includes(3)); // true
```

`map`, `filter`, and `reduce` are the most important. Learn them well — they replace
most manual loops in real code.

### Exercise 10

1. Create an array of 5 numbers. Print the sum using `reduce`.
2. From `[1,2,3,4,5,6]`, make a new array of only the odd numbers.
3. Turn `["a","b","c"]` into `["A","B","C"]` using `map`.

---

## 11. Objects

An **object** stores related data as **key-value pairs**. Use it when data has named
fields rather than a simple list.

```js
let person = {
  name: "Asha",
  age: 25,
  isStudent: true,
};
```

### Reading and changing properties

```js
console.log(person.name);     // "Asha"  (dot notation)
console.log(person["age"]);   // 25      (bracket notation)

person.age = 26;              // change
person.city = "Mumbai";       // add a new property
delete person.isStudent;      // remove a property
```

### Methods — functions inside objects

```js
let calculator = {
  value: 0,
  add(n) {
    this.value += n;
    return this.value;
  },
};

console.log(calculator.add(5)); // 5
console.log(calculator.add(3)); // 8
```

`this` refers to the object the method belongs to.

### Arrays of objects (very common)

```js
let users = [
  { name: "Asha", age: 25 },
  { name: "Ravi", age: 30 },
];

users.forEach((u) => console.log(`${u.name} is ${u.age}`));
```

### Looping over an object's keys

```js
let person = { name: "Asha", age: 25 };

for (let key in person) {
  console.log(key, person[key]);
}

Object.keys(person);   // ["name", "age"]
Object.values(person); // ["Asha", 25]
```

### Exercise 11

1. Create an object for a book (title, author, year). Print each property.
2. Make an array of 3 book objects and loop through printing their titles.
3. Add a method `describe()` to a book object that returns `"Title by Author"`.

---

## 12. Strings

Strings are text. They come with many built-in helpers.

```js
let text = "Hello, World";

console.log(text.length);        // 12
console.log(text.toUpperCase()); // "HELLO, WORLD"
console.log(text.toLowerCase()); // "hello, world"
console.log(text.indexOf("W"));  // 7
console.log(text.includes("World")); // true
console.log(text.slice(0, 5));   // "Hello"
console.log(text.replace("World", "JS")); // "Hello, JS"
console.log(text.trim());        // removes spaces at start/end
```

### Splitting and joining

```js
let csv = "apple,banana,cherry";
let list = csv.split(",");   // ["apple", "banana", "cherry"]
let back = list.join(" | "); // "apple | banana | cherry"
```

### Template literals (recap)

```js
let name = "Asha";
let age = 25;
console.log(`${name} is ${age} years old.`); // Asha is 25 years old.
```

### Accessing characters

```js
let word = "code";
console.log(word[0]);        // "c"
console.log(word.charAt(1)); // "o"
```

### Exercise 12

1. Ask for a sentence and print how many characters it has.
2. Reverse a string (hint: `split("")`, `reverse()`, `join("")`).
3. Count how many words are in a sentence using `split(" ")`.

---

## 13. The DOM — Making Web Pages Interactive

The **DOM** (Document Object Model) is the browser's representation of the page.
JavaScript can read and change it: find elements, change text, change styles, add or
remove things. This is where JS becomes visual and fun.

Start with this HTML file so the examples have something to work with:

```html
<!DOCTYPE html>
<html>
  <body>
    <h1 id="title">Hello</h1>
    <p class="message">Original text</p>
    <button id="myBtn">Click me</button>
    <ul id="list"></ul>

    <script>
      // JS goes here (or in a linked file)
    </script>
  </body>
</html>
```

### Selecting elements

```js
// By id (returns one element)
let title = document.getElementById("title");

// Modern, flexible way — uses CSS selectors
let heading = document.querySelector("#title");   // first match
let msg = document.querySelector(".message");      // by class
let allItems = document.querySelectorAll("li");    // all matches (a list)
```

`querySelector` is the one to learn — it uses the same selectors as CSS.

### Changing content and style

```js
let title = document.querySelector("#title");

title.textContent = "New Heading";       // change text
title.style.color = "blue";               // change CSS
title.classList.add("highlight");          // add a CSS class
title.classList.remove("highlight");       // remove a class
title.classList.toggle("active");          // add if missing, remove if present
```

### Creating and adding elements

```js
let list = document.querySelector("#list");

let item = document.createElement("li"); // make a new <li>
item.textContent = "First item";          // give it text
list.appendChild(item);                    // add it to the page
```

### Reading input values

```html
<input id="nameInput" type="text" />
```

```js
let input = document.querySelector("#nameInput");
console.log(input.value); // whatever the user typed
```

### Exercise 13

1. Change the page heading text with JavaScript.
2. Create three `<li>` elements in a loop and add them to the list.
3. Read a text input's value and print it to the console.

---

## 14. Events

An **event** is something that happens on the page: a click, a key press, a form
submit. You run code in response using an **event listener**.

```js
let button = document.querySelector("#myBtn");

button.addEventListener("click", function () {
  console.log("Button was clicked!");
});
```

Or with an arrow function:

```js
button.addEventListener("click", () => {
  alert("Clicked!");
});
```

### Common events

- `click` — mouse click
- `input` — user types in a field (fires on every keystroke)
- `submit` — a form is submitted
- `keydown` / `keyup` — keyboard keys
- `mouseover` / `mouseout` — hover

### The event object

The listener receives an `event` object with details:

```js
input.addEventListener("input", (event) => {
  console.log(event.target.value); // current text in the field
});
```

### A full interactive example

```html
<input id="field" placeholder="Type here" />
<p id="output"></p>

<script>
  let field = document.querySelector("#field");
  let output = document.querySelector("#output");

  field.addEventListener("input", (e) => {
    output.textContent = "You typed: " + e.target.value;
  });
</script>
```

As you type, the paragraph updates live. That's the core loop of interactive web apps:
**event happens → read state → update the DOM.**

### Exercise 14

1. Add a button that changes the page background color when clicked.
2. Add an input that shows its text in uppercase in a paragraph as the user types.
3. Make a counter: a button that increases a number shown on the page each click.

---

## 15. Error Handling

Code can fail: bad input, missing data, network problems. Handle errors so your
program doesn't crash.

### try...catch

```js
try {
  let result = riskyOperation(); // might throw an error
  console.log(result);
} catch (error) {
  console.log("Something went wrong:", error.message);
}
```

- Code in `try` runs normally.
- If it throws an error, execution jumps to `catch` instead of crashing.

### A practical example

```js
function parseAge(text) {
  let age = Number(text);
  if (isNaN(age)) {
    throw new Error("Not a valid number");
  }
  return age;
}

try {
  console.log(parseAge("25"));    // 25
  console.log(parseAge("hello")); // throws
} catch (e) {
  console.log("Error:", e.message); // Error: Not a valid number
}
```

### throw — raise your own error

Use `throw new Error("message")` to signal that something is wrong on purpose.

### finally — always runs

```js
try {
  doWork();
} catch (e) {
  console.log("failed");
} finally {
  console.log("This runs no matter what");
}
```

### Exercise 15

1. Write a function that divides two numbers but throws an error if dividing by zero.
2. Wrap a `Number(prompt(...))` call in try/catch and handle non-numeric input.

---

## 16. Capstone Project — To-Do List

Bring everything together: variables, functions, arrays, objects, the DOM, and events.
Build a working to-do list in one HTML file. Create `todo.html` and open it in a browser.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My To-Do List</title>
    <style>
      body { font-family: sans-serif; max-width: 400px; margin: 40px auto; }
      .done { text-decoration: line-through; color: gray; }
      li { cursor: pointer; margin: 6px 0; }
    </style>
  </head>
  <body>
    <h1>To-Do List</h1>
    <input id="taskInput" placeholder="Add a task..." />
    <button id="addBtn">Add</button>
    <ul id="taskList"></ul>

    <script>
      // 1. Grab the elements we need
      const input = document.querySelector("#taskInput");
      const addBtn = document.querySelector("#addBtn");
      const list = document.querySelector("#taskList");

      // 2. Store tasks in an array of objects
      let tasks = [];

      // 3. Draw the current tasks on the page
      function render() {
        list.innerHTML = ""; // clear first

        tasks.forEach((task, index) => {
          const li = document.createElement("li");
          li.textContent = task.text;

          if (task.done) {
            li.classList.add("done");
          }

          // Click a task to toggle done/undone
          li.addEventListener("click", () => {
            tasks[index].done = !tasks[index].done;
            render();
          });

          list.appendChild(li);
        });
      }

      // 4. Add a new task
      function addTask() {
        const text = input.value.trim();
        if (text === "") return; // ignore empty input

        tasks.push({ text: text, done: false });
        input.value = ""; // clear the box
        render();
      }

      // 5. Wire up events
      addBtn.addEventListener("click", addTask);
      input.addEventListener("keydown", (e) => {
        if (e.key === "Enter") addTask();
      });
    </script>
  </body>
</html>
```

### What this project teaches

- **Arrays & objects:** each task is an object `{ text, done }` in a `tasks` array.
- **Functions:** `render()` and `addTask()` break the work into clear pieces.
- **The DOM:** selecting, creating, and updating elements.
- **Events:** click to add, click to toggle, Enter key to add.
- **State → render pattern:** change the data, then redraw. This is the foundation of
  every modern framework (React, Vue, Angular).

### Extend it (challenges)

1. Add a **Delete** button next to each task.
2. Show a count of remaining (not done) tasks.
3. Add a **"Clear completed"** button.
4. Save tasks in `localStorage` so they survive a page refresh:
   ```js
   localStorage.setItem("tasks", JSON.stringify(tasks));
   let saved = JSON.parse(localStorage.getItem("tasks")) || [];
   ```

---

## Where to Go Next

Once the fundamentals above feel comfortable:

- **Asynchronous JS:** `setTimeout`, Promises, `async/await`, and `fetch` for calling APIs.
- **ES modules:** `import` / `export` to split code across files.
- **Node.js:** run JavaScript outside the browser; build tools and servers.
- **A framework:** React, Vue, or Angular — but only after solid vanilla JS.

### How to keep learning

- Build small projects (calculator, quiz, weather app using a public API).
- Read [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript) — the
  best JavaScript reference.
- Practice daily. Consistency beats intensity.

Happy coding!

---

## 17. Async JavaScript — Promises, async/await, fetch

So far every line of code ran top to bottom, instantly. But some tasks take **time**:
downloading data, calling an AI model, reading a file. These are **asynchronous** —
JavaScript starts them, keeps going, and deals with the result when it arrives.

This section is the gateway to AI work, because every AI API call is asynchronous.

### The problem async solves

If JavaScript waited (froze) for every slow task, the whole page would hang. Instead
it says "start this, tell me when it's done" and moves on.

### Callbacks (the old way — just so you recognize it)

```js
setTimeout(() => {
  console.log("This runs after 2 seconds");
}, 2000);

console.log("This runs first");
```

`setTimeout` schedules work for later. Notice "This runs first" prints before the
delayed message. That's async in action.

### Promises

A **Promise** represents a value that isn't ready yet. It will either **resolve**
(success) or **reject** (failure).

```js
const promise = doSomethingSlow();

promise
  .then((result) => console.log("Success:", result))
  .catch((error) => console.log("Failed:", error));
```

- `.then(...)` runs when it succeeds.
- `.catch(...)` runs if it fails.

### async / await (the modern, readable way)

`async/await` lets you write asynchronous code that *reads* like normal top-to-bottom
code. This is what you'll use most.

```js
async function loadData() {
  try {
    const result = await doSomethingSlow(); // "wait here" without freezing the page
    console.log("Success:", result);
  } catch (error) {
    console.log("Failed:", error);
  }
}

loadData();
```

- `await` pauses *inside the function* until the promise settles.
- `await` only works inside an `async` function.
- Wrap it in `try/catch` to handle failures (same pattern as Section 15).

### fetch — getting data from the internet

`fetch` is the built-in way to request data from a URL. It returns a promise.

```js
async function getUser() {
  const response = await fetch("https://jsonplaceholder.typicode.com/users/1");
  const data = await response.json(); // parse the JSON body (also async)
  console.log(data.name);
}

getUser();
```

Two `await`s are common: one for the response, one for `.json()` which reads the body.

### Why two awaits?

1. `await fetch(...)` — wait for the server to respond (headers arrive).
2. `await response.json()` — wait to read and parse the full body into an object.

### Exercise 17

1. Use `fetch` to get `https://jsonplaceholder.typicode.com/todos/1` and print its title.
2. Write an `async` function that fetches a user and prints their email, with
   `try/catch` to handle errors.
3. Fetch a list from `.../users` and use `.map()` to print just the names.

---

## 18. AI in JavaScript — Your First AI Feature

JavaScript can absolutely do AI. You don't need Python. There are two main approaches,
and both build directly on the async skills from Section 17.

### The two approaches

**A) Call a hosted AI model over an API.** A powerful model runs on a company's
servers (OpenAI, Anthropic, Google Gemini). You send text with `fetch`, get a reply.
This is how most real AI apps work.

**B) Run a model directly in the browser.** Libraries like **ml5.js**,
**TensorFlow.js**, and **Transformers.js** load a model into the page itself — no
server, no API key. Great for learning and small models.

We'll do a beginner-friendly example of each.

### Approach A — Calling an AI API

The key insight: an AI API call is **just a `fetch`** (Section 17) with a prompt in
the body. Everything you already learned applies.

```js
async function askAI(question) {
  const response = await fetch("https://api.openai.com/v1/chat/completions", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      "Authorization": "Bearer YOUR_API_KEY", // never hard-code real keys in frontend code!
    },
    body: JSON.stringify({
      model: "gpt-4o-mini",
      messages: [{ role: "user", content: question }],
    }),
  });

  const data = await response.json();
  return data.choices[0].message.content;
}

// Usage:
askAI("Explain variables to a 10 year old")
  .then((answer) => console.log(answer))
  .catch((err) => console.log("Error:", err.message));
```

> **Security note for freshers:** Never put a real API key in browser/frontend code —
> anyone can read it. In real apps the key lives on a **backend server** (e.g. Node.js),
> and the browser calls *your* server, which then calls the AI. For learning, run these
> examples in Node or keep keys in environment variables, not in public code.

### Approach B — Run a model in the browser with ml5.js (no key, no server)

**ml5.js** is a beginner-friendly library built on TensorFlow.js. Here's a complete,
runnable **sentiment analyzer** — it guesses whether text is positive or negative.
Save as `sentiment.html` and open in a browser.

```html
<!DOCTYPE html>
<html>
  <head>
    <title>AI Sentiment Analyzer</title>
    <script src="https://unpkg.com/ml5@0.12.2/dist/ml5.min.js"></script>
    <style>
      body { font-family: sans-serif; max-width: 480px; margin: 40px auto; }
      textarea { width: 100%; height: 80px; }
      #result { font-size: 1.3em; margin-top: 12px; font-weight: bold; }
    </style>
  </head>
  <body>
    <h1>Is this text positive or negative?</h1>
    <textarea id="text">I love learning JavaScript, it is amazing!</textarea>
    <button id="analyzeBtn">Analyze</button>
    <p id="result"></p>

    <script>
      // 1. Load the pre-trained sentiment model
      const sentiment = ml5.sentiment("movieReviews", () => {
        console.log("Model loaded and ready!");
      });

      const button = document.querySelector("#analyzeBtn");
      const textArea = document.querySelector("#text");
      const result = document.querySelector("#result");

      // 2. When clicked, analyze the text
      button.addEventListener("click", () => {
        const prediction = sentiment.predict(textArea.value);
        const score = prediction.score; // 0 (negative) to 1 (positive)

        const mood = score > 0.5 ? "😊 Positive" : "😟 Negative";
        result.textContent = `${mood}  (score: ${score.toFixed(2)})`;
      });
    </script>
  </body>
</html>
```

### What this AI example teaches

- **Loading a model** happens asynchronously — the callback fires when it's ready
  (Section 17's async ideas again).
- **DOM + events** (Sections 13–14): read the textarea, update the result on click.
- **Conditionals** (Section 7): the ternary turns a score into a label.
- It's real machine learning running entirely in the browser — no server, no API key.

### Other beginner-friendly browser AI demos to try

- **Image classification** with ml5.js `imageClassifier` — point it at a photo, it
  names what it sees (uses a pre-trained MobileNet model).
- **Transformers.js** (Hugging Face) — run modern transformer models in the browser:
  ```js
  import { pipeline } from "https://cdn.jsdelivr.net/npm/@xenova/transformers";
  const classifier = await pipeline("sentiment-analysis");
  const output = await classifier("I love this!");
  console.log(output); // [{ label: "POSITIVE", score: 0.99 }]
  ```

### How to teach AI to freshers (suggested order)

1. Master **async/await + fetch** (Section 17) — this is non-negotiable groundwork.
2. Do a **browser model demo** first (ml5.js sentiment or image classifier). It's
   visual, needs no API key, and gives an instant "wow".
3. Then build an **API-based feature** in Node.js, keeping the key on the server.
4. Finally, combine with the DOM/events skills to ship a small AI web app.

### Honest limitations

- JavaScript is excellent for **using** models and shipping AI features in web apps.
- For heavy model **training** and cutting-edge research, Python still has the richer
  ecosystem (PyTorch, TensorFlow, scikit-learn).
- Large models can't fully run in a browser — they need a server or a hosted API.

### Exercise 18

1. Run the sentiment analyzer and test it with 5 different sentences. Note where it's
   right and where it's wrong.
2. Modify it so an empty textarea shows "Please enter some text" instead of analyzing.
3. (Advanced) Try the ml5.js `imageClassifier` with an `<img>` on the page and print
   the top prediction.
4. (Advanced) Build a tiny Node.js script that calls an AI API and prints the reply —
   keep the key in an environment variable, not in the code.

---

## 19. Truthy & Falsy Values

In a condition (like `if`), JavaScript doesn't need a strict `true`/`false`. It
treats some values as "truthy" and some as "falsy". Beginners trip on this constantly,
so it's worth learning early.

### The falsy values (memorize this short list)

Only these are **falsy** — everything else is **truthy**:

```js
false
0          // the number zero
""         // empty string
null
undefined
NaN        // "Not a Number"
```

### Everything else is truthy

```js
if ("hello") console.log("runs");   // non-empty string is truthy
if (42) console.log("runs");        // any non-zero number is truthy
if ([]) console.log("runs");        // an empty array is truthy!
if ({}) console.log("runs");        // an empty object is truthy!
```

> **Common surprise:** empty array `[]` and empty object `{}` are **truthy**, even
> though they feel "empty". To check if an array is empty, test its length:
> `if (arr.length === 0)`.

### Using this in practice

```js
let name = "";

if (name) {
  console.log("Has a name");
} else {
  console.log("Name is empty"); // this runs — "" is falsy
}
```

### Short-circuit tricks (ES6-era patterns)

```js
// OR (||) — use a fallback when the value is falsy
let username = userInput || "Guest";
// if userInput is "" / null / undefined, username becomes "Guest"

// AND (&&) — run the right side only if the left is truthy
isLoggedIn && showDashboard();

// Nullish coalescing (??) — fallback ONLY for null/undefined (ES2020)
let count = userCount ?? 0;
// unlike ||, this keeps 0 and "" as valid values
```

The difference between `||` and `??` matters: `0 || 5` gives `5` (because `0` is
falsy), but `0 ?? 5` gives `0` (because `0` is not null/undefined). Use `??` when
`0` or `""` are valid values you want to keep.

### Exercise 19

1. Predict the output before running: `if ("0") console.log("A"); else console.log("B");`
   (Trick: `"0"` is a non-empty string.)
2. Use `||` to default a missing `city` variable to `"Unknown"`.
3. Explain the difference between `let x = 0 || 10;` and `let x = 0 ?? 10;`.

---

## 20. Destructuring & Spread/Rest

These are **ES6+** features you'll see everywhere in modern JavaScript. They make code
shorter and clearer.

### Array destructuring — unpack by position

```js
const colors = ["red", "green", "blue"];

const [first, second] = colors;
console.log(first);  // "red"
console.log(second); // "green"

// Skip items with a comma:
const [, , third] = colors;
console.log(third);  // "blue"
```

### Object destructuring — unpack by key name

```js
const user = { name: "Asha", age: 25, city: "Mumbai" };

const { name, age } = user;
console.log(name); // "Asha"
console.log(age);  // 25

// Rename while unpacking:
const { name: fullName } = user;
console.log(fullName); // "Asha"

// Default value if the key is missing:
const { country = "India" } = user;
console.log(country); // "India"
```

Destructuring in function parameters is very common:

```js
function greet({ name, age }) {
  console.log(`${name} is ${age}`);
}
greet(user); // Asha is 25
```

### Spread (`...`) — expand items out

```js
// Copy and combine arrays
const a = [1, 2];
const b = [3, 4];
const combined = [...a, ...b]; // [1, 2, 3, 4]

// Copy and extend objects
const base = { name: "Asha", age: 25 };
const updated = { ...base, age: 26 }; // { name: "Asha", age: 26 }
```

Spread is the standard way to copy an array/object without mutating the original.

### Rest (`...`) — gather items in

Same `...` syntax, opposite job: collect the remaining items into one variable.

```js
// Rest in destructuring
const [winner, ...others] = ["gold", "silver", "bronze"];
console.log(winner); // "gold"
console.log(others); // ["silver", "bronze"]

// Rest in function parameters — accept any number of arguments
function sum(...numbers) {
  return numbers.reduce((total, n) => total + n, 0);
}
console.log(sum(1, 2, 3, 4)); // 10
```

### Exercise 20

1. Destructure `{ title: "JS", pages: 300 }` into two variables and print them.
2. Use spread to merge `[1,2]` and `[3,4]` into one array.
3. Write a function `max(...nums)` that returns the largest of any number of arguments.

---

## 21. Working with JSON

**JSON** (JavaScript Object Notation) is the standard text format for sending data
between a browser and a server. It looks like a JavaScript object but is a **string**.

```json
{
  "name": "Asha",
  "age": 25,
  "hobbies": ["reading", "coding"]
}
```

### The two methods you need

```js
// Object -> JSON string (to send/store it)
const user = { name: "Asha", age: 25 };
const text = JSON.stringify(user);
console.log(text); // '{"name":"Asha","age":25}'

// JSON string -> Object (to use it)
const back = JSON.parse(text);
console.log(back.name); // "Asha"
```

- `JSON.stringify(obj)` — turn an object into a string.
- `JSON.parse(str)` — turn a JSON string back into an object.

### Why it matters

- `fetch` responses (Section 17) are JSON — that's why you call `response.json()`.
- `localStorage` only stores strings, so you `stringify` to save and `parse` to load
  (you saw this in the to-do capstone).

```js
// Save an array of tasks to the browser
localStorage.setItem("tasks", JSON.stringify(tasks));

// Load it back
const saved = JSON.parse(localStorage.getItem("tasks")) || [];
```

### Pretty-printing (handy for debugging)

```js
console.log(JSON.stringify(user, null, 2)); // indented, readable output
```

### Exercise 21

1. Turn an object into a JSON string and print it.
2. Parse the string `'{"x":1,"y":2}'` and print `x + y`.
3. Save an array to `localStorage`, reload the page, and read it back.

---

## 22. Debugging & Reading Errors

Every programmer hits errors constantly — that's normal. The skill is reading them
calmly and finding the cause. This section is small but one of the most valuable.

### console methods beyond log

```js
console.log("normal message");
console.error("something failed"); // shows in red
console.warn("careful!");           // shows a warning
console.table([{ a: 1 }, { a: 2 }]); // prints arrays/objects as a table
```

### Reading an error message

A typical error looks like:

```
Uncaught TypeError: Cannot read properties of undefined (reading 'name')
    at script.js:12
```

Read it in order:

- **TypeError** — the kind of error.
- **Cannot read properties of undefined (reading 'name')** — you tried `something.name`
  but `something` was `undefined`.
- **at script.js:12** — the file and line number. Start there.

### The most common beginner errors

| Error | Usual cause |
|-------|-------------|
| `undefined is not a function` | Misspelled a method, or called something that isn't a function |
| `Cannot read properties of undefined` | Used `.x` on a variable that has no value yet |
| `is not defined` | Used a variable name that was never declared (or a typo) |
| `Unexpected token` | A syntax mistake — missing `)`, `}`, `,` or quote |

### How to debug, step by step

1. **Read the whole error** — the type, the message, and the line number.
2. **Open the line** it points to and look just above it too.
3. **`console.log` the suspicious values** right before the failing line to see what
   they actually are.
4. **Check assumptions** — is that variable really an array? Really defined yet?
5. **Use breakpoints** — in the browser's **Sources** tab, click a line number to
   pause execution there and inspect every variable. More powerful than `console.log`.

### debugger statement

Drop this line in your code to pause there automatically when dev tools are open:

```js
function buggy(data) {
  debugger; // execution pauses here so you can inspect `data`
  return data.value;
}
```

### Mindset

Errors are clues, not failures. A red message with a line number is JavaScript
*helping* you. Read it slowly — most bugs are a typo, a wrong type, or using a value
before it exists.

### Exercise 22

1. Write code that triggers `Cannot read properties of undefined`, read the message,
   then fix it.
2. Use `console.table` to print an array of 3 objects.
3. Add a `debugger` statement inside a function and watch it pause in the browser.

---

## 23. Object-Oriented Programming (OOP) with Classes

**Object-Oriented Programming** is a way of organizing code around **objects** —
bundles of data (properties) and behavior (methods) that belong together. Instead of
loose variables and functions, you model real things: a `User`, a `Car`, a `BankAccount`.

JavaScript got a clean `class` syntax in **ES6 (ES2015)**. We'll build it up keyword
by keyword so nothing is skipped.

### Why OOP?

Imagine tracking 100 users. Without OOP you'd juggle separate arrays for names, ages,
emails. With OOP, each user is one self-contained object that knows its own data and
what it can do. Code becomes organized, reusable, and easier to reason about.

### The four pillars of OOP

1. **Encapsulation** — bundle data and methods together; hide internal details.
2. **Abstraction** — expose a simple interface, hide the complexity.
3. **Inheritance** — a class can build on another class.
4. **Polymorphism** — different classes can share a method name but behave differently.

We'll see each one below.

---

### Step 1 — `class` and `new`

A **class** is a blueprint. An **object** (or **instance**) is a real thing built
from that blueprint using the `new` keyword.

```js
class Dog {
  // body goes here
}

const myDog = new Dog(); // create an instance with `new`
console.log(myDog); // Dog {}
```

- `class` — keyword that declares a class. Name it with a capital letter (`Dog`, `User`).
- `new` — keyword that creates a new instance from the class.

---

### Step 2 — `constructor` and `this`

The **constructor** is a special method that runs automatically when you write `new`.
It sets up the object's starting data. **`this`** refers to the specific instance
being created.

```js
class Dog {
  constructor(name, breed) {
    this.name = name;   // store data on THIS instance
    this.breed = breed;
  }
}

const d1 = new Dog("Rex", "Labrador");
const d2 = new Dog("Bella", "Beagle");

console.log(d1.name); // "Rex"
console.log(d2.name); // "Bella"
```

- `constructor(...)` — runs once per `new`. Receives the arguments you pass.
- `this` — the instance currently being built. `this.name = name` saves data onto it.
- Each instance (`d1`, `d2`) has its **own** independent copy of the data.

---

### Step 3 — Methods (behavior)

**Methods** are functions that belong to the class. Every instance can use them.

```js
class Dog {
  constructor(name) {
    this.name = name;
  }

  bark() {
    console.log(`${this.name} says Woof!`);
  }

  describe() {
    return `This dog is called ${this.name}`;
  }
}

const d = new Dog("Rex");
d.bark();                  // Rex says Woof!
console.log(d.describe()); // This dog is called Rex
```

Methods use `this` to access the instance's own data. No `function` keyword is
needed inside a class — just the method name and parentheses.

---

### Step 4 — Encapsulation with private fields (`#`)

By default all properties are public (anyone can read/change them). **Private fields**,
written with a `#` prefix (**ES2022**), can only be accessed *inside* the class. This
is **encapsulation** — protecting internal data.

```js
class BankAccount {
  #balance = 0; // private field — cannot be touched from outside

  constructor(owner) {
    this.owner = owner; // public
  }

  deposit(amount) {
    if (amount <= 0) return;
    this.#balance += amount;
  }

  getBalance() {
    return this.#balance;
  }
}

const acc = new BankAccount("Asha");
acc.deposit(100);
console.log(acc.getBalance()); // 100
console.log(acc.owner);        // "Asha"
// console.log(acc.#balance);  // SyntaxError — private, no outside access
```

- `#balance` — a private field; only methods inside the class can use it.
- This forces changes to go through `deposit()`, which can validate the amount.

---

### Step 5 — Getters and setters (`get` / `set`)

**Getters** and **setters** let you access a method *like* a property. Useful for
computed values or validated updates.

```js
class Circle {
  constructor(radius) {
    this.radius = radius;
  }

  get area() {               // called WITHOUT parentheses
    return Math.PI * this.radius ** 2;
  }

  set diameter(value) {
    this.radius = value / 2;
  }
}

const c = new Circle(5);
console.log(c.area);   // 78.53... — no () needed, it's a getter
c.diameter = 20;       // runs the setter
console.log(c.radius); // 10
```

- `get name()` — read a value computed on the fly, accessed like `c.area`.
- `set name(value)` — intercept assignment, accessed like `c.diameter = 20`.

---

### Step 6 — `static` members

**Static** methods and properties belong to the **class itself**, not to instances.
Use them for helpers and shared constants.

```js
class MathHelper {
  static PI = 3.14159; // static property

  static square(n) {   // static method
    return n * n;
  }
}

console.log(MathHelper.square(4)); // 16  — called on the class, not an instance
console.log(MathHelper.PI);        // 3.14159
// const m = new MathHelper(); m.square(4); // ❌ won't work — static is on the class
```

- `static` — attaches a member to the class. Call it as `ClassName.method()`.
- Common real example: `Array.isArray([])`, `Object.keys(obj)` are static methods.

---

### Step 7 — Inheritance with `extends` and `super`

**Inheritance** lets a class reuse and extend another class.

- `extends` — makes a **child** class inherit from a **parent** class.
- `super(...)` — calls the parent's constructor (must run before using `this`).
- `super.method()` — calls a parent method from the child.

```js
class Animal {
  constructor(name) {
    this.name = name;
  }

  eat() {
    console.log(`${this.name} is eating.`);
  }

  speak() {
    console.log(`${this.name} makes a sound.`);
  }
}

class Dog extends Animal {       // Dog inherits from Animal
  constructor(name, breed) {
    super(name);                 // call Animal's constructor FIRST
    this.breed = breed;
  }

  // Polymorphism: override the parent's method
  speak() {
    console.log(`${this.name} barks!`);
  }

  info() {
    super.speak();               // still call the parent version if you want
    console.log(`${this.name} is a ${this.breed}.`);
  }
}

const d = new Dog("Rex", "Labrador");
d.eat();   // Rex is eating.   (inherited from Animal)
d.speak(); // Rex barks!       (overridden in Dog)
d.info();  // Rex makes a sound. / Rex is a Labrador.
```

- `extends` — sets up the parent-child relationship.
- `super(name)` — runs the parent constructor; **required** before `this` in a child
  constructor.
- Overriding `speak()` in `Dog` is **polymorphism**: same method name, different behavior.

---

### Step 8 — `instanceof`

The **`instanceof`** operator checks whether an object was built from a given class
(including its parent classes).

```js
console.log(d instanceof Dog);    // true
console.log(d instanceof Animal); // true  — because Dog extends Animal
console.log(d instanceof Array);  // false
```

---

### The `this` keyword — a common gotcha

`this` depends on *how* a method is called. If you pass a method as a callback, `this`
can be lost. Arrow functions fix this because they keep the surrounding `this`.

```js
class Timer {
  constructor() {
    this.seconds = 0;
  }

  start() {
    // Arrow function keeps `this` pointing at the Timer instance
    setInterval(() => {
      this.seconds++;
      console.log(this.seconds);
    }, 1000);
  }
}
```

If you used a regular `function () {...}` inside `setInterval`, `this` would **not**
be the Timer, and `this.seconds` would fail. This is a classic beginner bug.

---

### A note on prototypes (what classes are built on)

Before ES6 classes, JavaScript did OOP with **constructor functions** and the
**prototype** chain. `class` is modern syntax sugar over that same system — nice to
know the name `prototype` exists, but you can build everything with `class`.

```js
// Old pre-ES6 style (recognize it, but prefer class):
function Dog(name) {
  this.name = name;
}
Dog.prototype.bark = function () {
  console.log(this.name + " woofs");
};
```

---

### Keyword cheat sheet

| Keyword | What it does |
|---------|--------------|
| `class` | Declares a class (blueprint) |
| `new` | Creates an instance from a class |
| `constructor` | Special method that runs on `new`, sets up data |
| `this` | Refers to the current instance |
| `extends` | Makes a class inherit from another |
| `super` | Calls the parent constructor or a parent method |
| `static` | Attaches a member to the class itself, not instances |
| `get` | Defines a getter (read a computed property) |
| `set` | Defines a setter (intercept an assignment) |
| `#field` | Declares a private field (encapsulation) |
| `instanceof` | Checks if an object came from a given class |
| `prototype` | The underlying mechanism classes are built on |

---

### Full worked example — putting it all together

```js
class Shape {
  constructor(name) {
    this.name = name;
  }

  area() {
    return 0; // base default; subclasses override
  }

  describe() {
    return `${this.name} has an area of ${this.area().toFixed(2)}`;
  }
}

class Rectangle extends Shape {
  constructor(width, height) {
    super("Rectangle");
    this.width = width;
    this.height = height;
  }

  area() {                      // polymorphism — override
    return this.width * this.height;
  }
}

class Circle extends Shape {
  #radius;                      // encapsulation — private

  constructor(radius) {
    super("Circle");
    this.#radius = radius;
  }

  get radius() {                // getter
    return this.#radius;
  }

  area() {                      // override
    return Math.PI * this.#radius ** 2;
  }

  static fromDiameter(d) {      // static factory method
    return new Circle(d / 2);
  }
}

const shapes = [new Rectangle(4, 5), new Circle(3), Circle.fromDiameter(10)];

shapes.forEach((s) => console.log(s.describe()));
// Rectangle has an area of 20.00
// Circle has an area of 28.27
// Circle has an area of 78.54

console.log(shapes[1] instanceof Shape); // true
```

This single example uses: `class`, `new`, `constructor`, `this`, `extends`, `super`,
`static`, `get`, a private `#` field, method overriding (polymorphism), and
`instanceof` — the complete OOP toolkit.

### Exercise 23

1. Create a `Person` class with `name` and `age`, and a `greet()` method.
2. Create a `Student` class that `extends Person`, adds a `grade`, and uses `super`.
3. Add a **private** `#password` field to a `User` class with a `checkPassword(guess)`
   method (never expose the password directly).
4. Add a `static` method `User.fromJSON(jsonString)` that parses JSON and returns a
   new `User` instance.
5. Create an array of mixed shapes and loop through calling a shared `area()` method
   (polymorphism in action).
