# JavaScript OOP — Complete Guide (Beginner → Architect)

A comprehensive, tiered guide to Object-Oriented Programming in JavaScript. It starts
at the absolute fundamentals and builds all the way to enterprise and architectural
concepts. Each topic has a plain explanation and runnable code.

> **How to use this guide:** Learn in order. The tiers build on each other.
> - **Tiers 1–4** are for freshers and should be mastered first.
> - **Tiers 5–7** are intermediate.
> - **Tiers 8–11** are advanced / architect-level — tackle them after writing real code.
>
> This is a companion to `javascript-from-scratch.md`. Finish the basics there first.

## Honest notes on JavaScript and OOP terminology

JavaScript's object model is **prototype-based**. ES6 `class` syntax is convenient
sugar over prototypes. A few terms from classical OOP (Java/C#) don't exist natively
and are achieved by **convention or pattern** in JS. This guide flags them clearly:

- **No real `protected`** — simulated by naming convention (`_name`) or closures/WeakMap.
- **No real `interface` or `abstract class` keyword** — implemented as patterns.
- **"Classical inheritance"** in JS still runs on prototypes underneath.
- **"Multiple inheritance"** isn't supported directly — mixins approximate it.

Where a concept is a pattern/convention rather than a language keyword, it says so.

---

## Table of Contents

**Tier 1 — Beginner**
1. [Object Fundamentals](#1-object-fundamentals)
2. [Class Fundamentals](#2-class-fundamentals)

**Tier 2 — The Four Pillars (in depth)**
3. [Encapsulation](#3-encapsulation)
4. [Abstraction](#4-abstraction)
5. [Inheritance](#5-inheritance)
6. [Polymorphism](#6-polymorphism)

**Tier 3 — The Prototype System**
7. [Prototypes & the Prototype Chain](#7-prototypes--the-prototype-chain)

**Tier 4 — Object Creation Patterns**
8. [Creating Objects — Every Approach](#8-creating-objects--every-approach)

**Tier 5 — Relationships & Composition**
9. [Object Relationships & Composition](#9-object-relationships--composition)

**Tier 6 — Object & Property Manipulation**
10. [Object Manipulation & Property Descriptors](#10-object-manipulation--property-descriptors)

**Tier 7 — Context, Binding, Immutability**
11. [this, Binding, Cloning & Immutability](#11-this-binding-cloning--immutability)

**Tier 8 — Metaprogramming**
12. [Reflection & Metaprogramming](#12-reflection--metaprogramming)

**Tier 9 — Principles**
13. [SOLID, GRASP & Architectural Principles](#13-solid-grasp--architectural-principles)

**Tier 10 — Design Patterns**
14. [Design Patterns](#14-design-patterns)

**Tier 11 — Enterprise / Architect**
15. [Enterprise, DDD & Event-Driven Design](#15-enterprise-ddd--event-driven-design)

**Appendix — Gap-Fillers** (WeakSet, Bridge, Flyweight, Symbol.species, Entity vs Value Object, Object Lifecycle)

**Appendix 2 — Advanced & Architectural** (internal slots `[[Get]]`/`[[Set]]`, reachability/WeakRef, decorators, metadata, dynamic imports, message passing, event-driven architecture, event sourcing, bounded context, domain event, MVC/MVP/MVVM, hexagonal/clean/onion, state machines, actor model, currying, partial application, composition)

---
---

# TIER 1 — BEGINNER

## 1. Object Fundamentals

### What is an object?

An **object** is a self-contained bundle of related **data** and **behavior**. Think
of a real-world thing: a car has data (color, speed) and behavior (accelerate, brake).

```js
const car = {
  // Properties (data / state)
  color: "red",
  speed: 0,

  // Methods (behavior)
  accelerate() {
    this.speed += 10;
  },
};
```

### Property (Attribute)

A **property** (also called an **attribute** or **field**) is a named value stored on
an object. `color` and `speed` above are properties.

```js
console.log(car.color); // "red" — dot notation
console.log(car["speed"]); // 0  — bracket notation
```

### Method

A **method** is a function stored as a property — the object's **behavior**.

```js
car.accelerate();
console.log(car.speed); // 10
```

### State vs Behavior

- **State** = the current values of an object's properties (the car's `speed` is `10`).
- **Behavior** = what the object can *do* (its methods, like `accelerate()`).

State changes over time; behavior stays the same. Calling `accelerate()` (behavior)
mutates `speed` (state).

```js
console.log(car.speed); // 0   — initial state
car.accelerate();        // behavior runs
console.log(car.speed); // 10  — state changed
```

### Object Identity

Each object has a unique **identity** in memory. Two objects with identical contents
are still *different* objects. Equality (`===`) on objects compares **identity**
(same reference), not contents.

```js
const a = { x: 1 };
const b = { x: 1 };
const c = a;

console.log(a === b); // false — same contents, different identity
console.log(a === c); // true  — c refers to the SAME object as a
```

### Primitive vs Reference Types (critical foundation)

This explains the result above. JavaScript has two value categories:

- **Primitives** (`string`, `number`, `boolean`, `null`, `undefined`, `symbol`,
  `bigint`) are copied **by value**.
- **Objects** (including arrays and functions) are handled **by reference** — the
  variable holds a pointer to the object, not the object itself.

```js
// Primitive — copied by value
let p1 = 10;
let p2 = p1; // copy of the value
p2 = 20;
console.log(p1); // 10 — unaffected

// Reference — shared pointer
let o1 = { n: 10 };
let o2 = o1; // same object, not a copy
o2.n = 20;
console.log(o1.n); // 20 — both point to the same object
```

This single concept explains most "why did my array change?!" bugs beginners hit.

### Object Wrappers (String, Number, Boolean)

Primitives aren't objects, yet `"hello".toUpperCase()` works. JavaScript temporarily
wraps the primitive in an **object wrapper** (`String`, `Number`, `Boolean`) so you can
call methods, then discards the wrapper.

```js
const s = "hello";
console.log(s.toUpperCase()); // "HELLO" — JS wrapped it in a String object briefly
console.log(typeof s);        // "string" — still a primitive
// Avoid `new String("hi")` — that creates an actual object and causes confusion.
```

### Nested Objects

Objects can contain other objects, modeling complex data.

```js
const user = {
  name: "Asha",
  address: {
    city: "Mumbai",
    geo: { lat: 19.07, lng: 72.87 },
  },
};

console.log(user.address.geo.lat); // 19.07

// Safe access when a level might be missing (optional chaining, ES2020):
console.log(user.address?.geo?.lat); // 19.07
console.log(user.job?.title);        // undefined (no crash)
```

### Exercise 1

1. Create a `book` object with properties and one method that returns a summary string.
2. Demonstrate reference behavior: copy an object into a second variable, change one,
   show both changed.
3. Build a nested object (a `company` with a `ceo` object) and read a deep property
   using optional chaining.

---

## 2. Class Fundamentals

### Class, Instance, `new`

A **class** is a blueprint. An **instance** is a concrete object built from it with
the `new` keyword.

```js
class Car {
  constructor(color) {
    this.color = color; // instance property
    this.speed = 0;
  }

  accelerate() {
    this.speed += 10;
  }
}

const myCar = new Car("red"); // myCar is an INSTANCE of Car
```

### Constructor

The **constructor** runs automatically on `new`. It initializes instance state.
`this` is the new instance being created.

```js
const c1 = new Car("blue");
const c2 = new Car("green");
console.log(c1.color, c2.color); // blue green — independent instances
```

### Class Fields (ES2022)

You can declare instance fields directly in the class body, outside the constructor.

```js
class Counter {
  count = 0;        // instance field with a default
  step = 1;

  increment() {
    this.count += this.step;
  }
}
```

### Static Properties and Methods

`static` members belong to the **class itself**, not instances. Use for shared
constants and helpers/factories.

```js
class MathUtil {
  static PI = 3.14159;        // static property

  static square(n) {          // static method
    return n * n;
  }
}

console.log(MathUtil.PI);        // 3.14159
console.log(MathUtil.square(5)); // 25
```

### Private Static Fields & Methods (ES2022)

Combine `static` with `#` for class-level private helpers.

```js
class IdGenerator {
  static #counter = 0;             // private static field

  static #next() {                 // private static method
    return ++IdGenerator.#counter;
  }

  static create() {
    return `id_${IdGenerator.#next()}`;
  }
}

console.log(IdGenerator.create()); // id_1
console.log(IdGenerator.create()); // id_2
```

### Static Initialization Blocks (ES2022)

A `static { ... }` block runs once when the class is defined — useful for complex
static setup.

```js
class Config {
  static settings = {};

  static {
    // runs once at class definition time
    Config.settings.env = "production";
    Config.settings.version = "1.0";
  }
}

console.log(Config.settings); // { env: "production", version: "1.0" }
```

### Readonly Properties (Convention)

JavaScript has no `readonly` keyword at runtime (that's TypeScript). To approximate
immutability of a property, use a getter with no setter, a private field, or
`Object.freeze` (covered in Tier 6).

```js
class Point {
  #x;
  #y;
  constructor(x, y) {
    this.#x = x;
    this.#y = y;
  }
  get x() { return this.#x; } // read-only from outside: no setter
  get y() { return this.#y; }
}

const p = new Point(1, 2);
console.log(p.x); // 1
p.x = 99;         // silently ignored (no setter) in non-strict; throws in strict mode
console.log(p.x); // 1
```

### Class Expressions & Anonymous Classes

Classes can be defined as **expressions** (assigned to a variable), and can be
**anonymous** (no name). Useful for dynamic creation.

```js
// Named class expression
const Animal = class AnimalClass {
  speak() { return "..."; }
};

// Anonymous class expression
const Widget = class {
  render() { return "<div>"; }
};

// Returning a class from a function (dynamic classes)
function makeModel(tableName) {
  return class {
    static table = tableName;
  };
}
const User = makeModel("users");
console.log(User.table); // "users"
```

### Computed Property Names (ES6)

Property/method names can be computed with `[ ]`.

```js
const key = "dynamicMethod";

class Dynamic {
  ["prop_" + 1] = "value"; // computed field name -> prop_1

  [key]() {                 // computed method name
    return "called";
  }
}

const d = new Dynamic();
console.log(d.prop_1);         // "value"
console.log(d.dynamicMethod()); // "called"
```

### Keyword recap (Tier 1)

| Keyword / Feature | Purpose | ES Version |
|-------------------|---------|------------|
| `class` | Declare a class | ES6 |
| `new` | Create an instance | ES1 |
| `constructor` | Initialize instance | ES6 |
| class fields | Declare fields in body | ES2022 |
| `static` | Class-level member | ES6 (fields ES2022) |
| `static #` | Private static member | ES2022 |
| `static { }` | Static init block | ES2022 |
| `[computed]` | Dynamic name | ES6 |

### Exercise 2

1. Write a `Temperature` class with a `celsius` field and a read-only `fahrenheit` getter.
2. Add a `static` method `Temperature.fromFahrenheit(f)` that returns a new instance.
3. Use a private static field to count how many instances have been created.

---
---

# TIER 2 — THE FOUR PILLARS

## 3. Encapsulation

**Encapsulation** means bundling data with the methods that operate on it, and
**hiding internal details** so outside code can't reach in and break invariants. You
expose a controlled interface; the internals stay private.

### Data Hiding — why it matters

Without hiding, anyone can set invalid state:

```js
// NO encapsulation — balance can go negative, be set to a string, etc.
const account = { balance: 100 };
account.balance = -9999; // nothing stops this
```

Encapsulation routes all changes through methods that enforce rules.

### Private Fields (`#`) — the modern way (ES2022)

```js
class BankAccount {
  #balance = 0; // truly private — enforced by the language

  deposit(amount) {
    if (amount <= 0) throw new Error("Deposit must be positive");
    this.#balance += amount;
  }

  withdraw(amount) {
    if (amount > this.#balance) throw new Error("Insufficient funds");
    this.#balance -= amount;
  }

  get balance() {
    return this.#balance; // read-only access
  }
}

const acc = new BankAccount();
acc.deposit(100);
console.log(acc.balance); // 100
// acc.#balance = 999;    // SyntaxError — cannot access private field
```

### Closures for Encapsulation (the classic pre-`#` technique)

Before private fields, privacy came from **closures**: variables inside a function are
invisible outside it, but inner functions can still use them.

```js
function createCounter() {
  let count = 0; // private — only the returned functions can see it

  return {
    increment() { count++; },
    get() { return count; },
  };
}

const counter = createCounter();
counter.increment();
console.log(counter.get()); // 1
console.log(counter.count); // undefined — truly hidden
```

### WeakMap for Private Data (another classic pattern)

A **`WeakMap`** keyed by the instance stores private data outside the object. When the
instance is garbage-collected, its private data is too (no memory leak).

```js
const _private = new WeakMap();

class User {
  constructor(password) {
    _private.set(this, { password });
  }

  checkPassword(guess) {
    return _private.get(this).password === guess;
  }
}

const u = new User("secret");
console.log(u.checkPassword("secret")); // true
console.log(u.password);                // undefined — not on the object
```

### Protected Members (Convention only)

JavaScript has **no `protected`** keyword. The convention is a leading underscore
`_name` to signal "internal, don't touch" — but it's not enforced.

```js
class Base {
  constructor() {
    this._internal = "treat as protected by convention";
  }
}
// _internal is still technically accessible — it's a signal, not a guarantee.
```

### Getters and Setters — controlled access

```js
class Temperature {
  #celsius = 0;

  get celsius() { return this.#celsius; }

  set celsius(value) {
    if (value < -273.15) throw new Error("Below absolute zero");
    this.#celsius = value;
  }

  get fahrenheit() { return this.#celsius * 9 / 5 + 32; }
}

const t = new Temperature();
t.celsius = 25;             // setter validates
console.log(t.fahrenheit);  // 77 — computed getter
```

### Exercise 3

1. Build a `Stack` class with a private `#items` array and `push`/`pop`/`peek`/`size`.
2. Rewrite it using the closure technique instead of `#`.
3. Add a setter that rejects invalid values and throws a clear error.

---

## 4. Abstraction

**Abstraction** means exposing a **simple, essential interface** while hiding the
complex implementation. Encapsulation hides *data*; abstraction hides *complexity*.
A driver uses a steering wheel (interface) without knowing the steering mechanics.

### Information Hiding

Expose *what* an object does, not *how*.

```js
class EmailService {
  // Public interface — simple
  send(to, message) {
    this.#connect();
    this.#authenticate();
    this.#transmit(to, message);
    this.#disconnect();
  }

  // Hidden complexity
  #connect() { /* ... */ }
  #authenticate() { /* ... */ }
  #transmit(to, msg) { /* ... */ }
  #disconnect() { /* ... */ }
}

// User only sees: service.send("a@b.com", "hi")
```

### Abstract Classes (Pattern — no native keyword)

JavaScript has **no `abstract` keyword**. You simulate an abstract class by preventing
direct instantiation and forcing subclasses to implement methods.

```js
class Shape {
  constructor() {
    if (new.target === Shape) {         // new.target = the class used with `new`
      throw new Error("Shape is abstract and cannot be instantiated directly");
    }
  }

  area() {
    throw new Error("Subclass must implement area()"); // abstract method
  }
}

class Square extends Shape {
  constructor(side) {
    super();
    this.side = side;
  }
  area() { return this.side ** 2; } // concrete implementation
}

// new Shape();        // Error — abstract
console.log(new Square(4).area()); // 16
```

### Interfaces (Pattern — no native keyword)

JavaScript has **no `interface` keyword** (that's TypeScript). An "interface" in JS is
an informal contract: a set of methods an object promises to provide. You can verify
it at runtime.

```js
// A "Comparable" interface = must have a compareTo(other) method
function assertComparable(obj) {
  if (typeof obj.compareTo !== "function") {
    throw new Error("Object must implement compareTo()");
  }
}

class Money {
  constructor(amount) { this.amount = amount; }
  compareTo(other) { return this.amount - other.amount; }
}

assertComparable(new Money(10)); // passes
```

> In TypeScript you'd write `interface Comparable { compareTo(o): number }` and get
> compile-time checking. In plain JS it's a convention plus optional runtime checks.

### Exercise 4

1. Create an abstract `PaymentMethod` class that throws if instantiated directly and
   declares an abstract `pay(amount)`.
2. Implement `CreditCard` and `PayPal` subclasses.
3. Write an `assertPayable(obj)` function that checks the object has a `pay` method.

---

## 5. Inheritance

**Inheritance** lets a class reuse and specialize another class. The child **is-a**
kind of the parent (a `Dog` is-a `Animal`).

### Classical Inheritance with `extends` / `super`

(In JS this is still prototype-based under the hood — see Tier 3.)

```js
class Animal {
  constructor(name) { this.name = name; }
  eat() { return `${this.name} eats`; }
}

class Dog extends Animal {
  constructor(name, breed) {
    super(name);        // Constructor Chaining — call parent constructor first
    this.breed = breed;
  }
  fetch() { return `${this.name} fetches`; }
}

const d = new Dog("Rex", "Lab");
console.log(d.eat());   // Rex eats  (inherited)
console.log(d.fetch()); // Rex fetches
```

### Constructor Chaining & `super`

- `super(args)` — calls the parent constructor. **Required** before using `this` in a
  subclass constructor.
- `super.method()` — calls a parent method (useful when overriding).

```js
class Logger {
  log(msg) { return `[LOG] ${msg}`; }
}
class TimestampLogger extends Logger {
  log(msg) {
    return super.log(`${Date.now()} ${msg}`); // extend, don't replace
  }
}
```

### Method Overriding

A subclass can redefine a parent method (same name, new behavior). This is the basis
of polymorphism (next section).

```js
class Bird extends Animal {
  eat() { return `${this.name} pecks seeds`; } // overrides Animal.eat
}
```

### Multilevel Inheritance

A chain: C extends B extends A.

```js
class A { a() { return "a"; } }
class B extends A { b() { return "b"; } }
class C extends B { c() { return "c"; } }

const obj = new C();
console.log(obj.a(), obj.b(), obj.c()); // a b c
```

### Hierarchical Inheritance

Multiple children share one parent.

```js
class Vehicle { move() { return "moving"; } }
class Car extends Vehicle {}
class Bike extends Vehicle {}
// Car and Bike both inherit from Vehicle
```

### Multiple Inheritance via Mixins

JavaScript does **not** support inheriting from multiple parents. **Mixins**
approximate it by copying behavior into a class. (Full treatment in Tier 5.)

```js
const Swimmer = (Base) => class extends Base {
  swim() { return "swimming"; }
};
const Flyer = (Base) => class extends Base {
  fly() { return "flying"; }
};

class Animal2 {}
class Duck extends Swimmer(Flyer(Animal2)) {}

const duck = new Duck();
console.log(duck.swim(), duck.fly()); // swimming flying
```

### Prototype Delegation

Inheritance in JS works by **delegation**: if an object lacks a property, the lookup
delegates up the prototype chain to its parent. Detailed in Tier 3.

### Exercise 5

1. Build `Employee` → `Manager` → `Director` multilevel inheritance.
2. Create a hierarchical set: `Shape` with `Circle`, `Square`, `Triangle` children.
3. Override `toString()` in each child to describe itself, calling `super` where useful.

---

## 6. Polymorphism

**Polymorphism** ("many forms") means the same interface works across different types.
Call `area()` on any shape and the right implementation runs.

### Subtype Polymorphism (the main one)

Different subclasses respond to the same method call in their own way.

```js
class Shape { area() { return 0; } }
class Circle extends Shape {
  constructor(r) { super(); this.r = r; }
  area() { return Math.PI * this.r ** 2; }
}
class Square extends Shape {
  constructor(s) { super(); this.s = s; }
  area() { return this.s ** 2; }
}

const shapes = [new Circle(2), new Square(3)];
shapes.forEach((s) => console.log(s.area())); // 12.56..., 9
// Same call `s.area()`, different behavior per type — polymorphism.
```

### Method Overriding (the mechanism)

Subtype polymorphism relies on overriding (seen in Section 5): each subclass provides
its own version of the shared method.

### Duck Typing

"If it walks like a duck and quacks like a duck, it's a duck." JavaScript cares about
whether an object *has* the method, not what class it is.

```js
function makeItSpeak(thing) {
  // We don't check the type — only that it can speak()
  return thing.speak();
}

makeItSpeak({ speak: () => "woof" }); // works — no class needed
makeItSpeak({ speak: () => "beep" }); // also works
```

### Ad-hoc Polymorphism

The same function behaves differently based on argument types/counts (JS has no true
overloading, so you branch inside one function).

```js
function add(a, b) {
  if (typeof a === "string") return a.concat(b); // strings -> concatenate
  return a + b;                                    // numbers -> sum
}
console.log(add(1, 2));       // 3
console.log(add("a", "b"));   // "ab"
```

### Parametric Polymorphism (Generics)

Code that works for any type uniformly. Plain JS is dynamically typed, so this is
"free"; TypeScript expresses it with generics `<T>`.

```js
// Works for an array of ANY type — parametric
function first(array) { return array[0]; }
console.log(first([1, 2, 3]));       // 1
console.log(first(["a", "b"]));      // "a"
// TypeScript: function first<T>(array: T[]): T { return array[0]; }
```

### Exercise 6

1. Create `Animal` subclasses that each override `makeSound()`; loop and call it.
2. Write a duck-typed `render(component)` that only requires a `.render()` method.
3. Write an ad-hoc `combine(a, b)` that merges arrays, concatenates strings, or adds
   numbers depending on input type.

---
---

# TIER 3 — THE PROTOTYPE SYSTEM

## 7. Prototypes & the Prototype Chain

This is the real engine beneath JavaScript objects. `class` is sugar; **prototypes**
are the mechanism. Understanding this tier is what separates intermediate from
beginner JS developers.

### What is a prototype?

Every JavaScript object has a hidden link to another object called its **prototype**.
When you access a property the object doesn't have, JS looks on the prototype, then
*its* prototype, and so on — the **prototype chain**.

```js
const animal = {
  eats: true,
  walk() { return "walking"; },
};

const rabbit = {
  jumps: true,
  __proto__: animal, // rabbit's prototype is animal
};

console.log(rabbit.jumps); // true  — own property
console.log(rabbit.eats);  // true  — found on prototype (animal)
console.log(rabbit.walk()); // walking — method found on prototype
```

### `[[Prototype]]`, `__proto__`, and `Object.getPrototypeOf`

- **`[[Prototype]]`** — the internal hidden slot holding the prototype link (spec term).
- **`__proto__`** — a legacy accessor to read/write it (works, but discouraged).
- **`Object.getPrototypeOf(obj)` / `Object.setPrototypeOf(obj, proto)`** — the modern,
  preferred API.

```js
console.log(Object.getPrototypeOf(rabbit) === animal); // true
// __proto__ is the old way to access the same [[Prototype]] slot.
```

### The `prototype` property (on functions/classes)

Confusingly, **`prototype`** (no underscores) is a different thing: it's a property on
**functions and classes**. When you call `new Fn()`, the new object's `[[Prototype]]`
is set to `Fn.prototype`.

```js
function Dog(name) {
  this.name = name;
}
Dog.prototype.bark = function () {
  return `${this.name} woofs`;
};

const d = new Dog("Rex");
console.log(d.bark());                              // Rex woofs
console.log(Object.getPrototypeOf(d) === Dog.prototype); // true
```

So: **`Fn.prototype`** is the object that becomes the **`[[Prototype]]`** of instances
created with `new Fn()`. Classes work identically — methods live on `Class.prototype`.

```js
class Cat {
  meow() { return "meow"; }
}
console.log(typeof Cat.prototype.meow); // "function" — methods live on the prototype
```

### The `constructor` property

Every `prototype` object has a **`constructor`** property pointing back to the
function/class that owns it.

```js
console.log(Dog.prototype.constructor === Dog); // true
console.log(d.constructor === Dog);             // true (found via the chain)
console.log(d.constructor.name);                // "Dog"
```

### The Object prototype (top of the chain)

Most chains end at **`Object.prototype`** (which provides `toString`, `hasOwnProperty`,
etc.), and *its* prototype is `null` — the end of the chain.

```js
const obj = {};
console.log(Object.getPrototypeOf(obj) === Object.prototype);        // true
console.log(Object.getPrototypeOf(Object.prototype));                // null — top
```

Full chain for a class instance:

```
d  →  Dog.prototype  →  Object.prototype  →  null
```

### Prototype Lookup Mechanism

When you read `obj.prop`:

1. Does `obj` have its own `prop`? Use it.
2. If not, follow `[[Prototype]]` and check there.
3. Repeat up the chain until found or `null` is reached (then `undefined`).

Writing is different: `obj.prop = x` almost always creates/updates an **own**
property on `obj` directly — it does **not** modify the prototype.

### Property Shadowing

If an object has its **own** property with the same name as one on its prototype, the
own property **shadows** (hides) the prototype's.

```js
const base = { greeting: "hello from base" };
const child = { __proto__: base };

console.log(child.greeting); // "hello from base" (from prototype)
child.greeting = "hello from child"; // creates an OWN property — shadows base
console.log(child.greeting); // "hello from child"
console.log(base.greeting);  // "hello from base" (unchanged)
```

### Own vs Inherited Properties

```js
const parent = { inherited: 1 };
const obj2 = Object.create(parent);
obj2.own = 2;

console.log(obj2.hasOwnProperty("own"));       // true
console.log(obj2.hasOwnProperty("inherited")); // false — it's inherited
console.log("inherited" in obj2);              // true — `in` checks the whole chain

// Safe, modern own-check (ES2022):
console.log(Object.hasOwn(obj2, "own"));       // true
```

### Prototype Mutation & Dynamic Extension

You can add to a prototype at runtime, and **all** existing instances instantly gain
the new method (because lookup is live, not copied).

```js
class Widget {}
const w = new Widget();

Widget.prototype.render = function () { return "rendered"; };
console.log(w.render()); // "rendered" — w gained the method after creation

// NOTE: Mutating built-in prototypes (e.g. Array.prototype) is strongly discouraged —
// it can break other code and libraries. Know it's possible; avoid doing it.
```

### Internal methods: `[[Construct]]` and `[[Call]]`

Functions have two internal operations:

- **`[[Call]]`** — runs when you call the function normally: `fn()`.
- **`[[Construct]]`** — runs when you use `new fn()`; it creates a fresh object, links
  its prototype, runs the body with `this` as that object, and returns it.

```js
function Person(name) { this.name = name; }

const a = Person("Asha"); // [[Call]] — `this` is NOT a new object; returns undefined
const b = new Person("Asha"); // [[Construct]] — makes & returns a new Person
console.log(a);        // undefined
console.log(b.name);   // "Asha"

// `new.target` tells you which path ran:
function Guard() {
  if (!new.target) throw new Error("Must call with new");
}
```

### Object Coercion (relevant to the object model)

When an object is used where a primitive is expected, JS **coerces** it by calling
`Symbol.toPrimitive`, then `valueOf()`, then `toString()`. (More on `Symbol.toPrimitive`
in Tier 8.)

```js
const money = {
  amount: 100,
  toString() { return `$${this.amount}`; },
  valueOf() { return this.amount; },
};

console.log(`${money}`);  // "$100"  — toString for string context
console.log(money + 10);  // 110     — valueOf for numeric context
```

### Visualizing the chain

```js
class Animal3 { eat() {} }
class Dog3 extends Animal3 { bark() {} }
const dog = new Dog3();

// dog → Dog3.prototype → Animal3.prototype → Object.prototype → null
console.log(Object.getPrototypeOf(dog) === Dog3.prototype);                 // true
console.log(Object.getPrototypeOf(Dog3.prototype) === Animal3.prototype);   // true
```

### Exercise 7

1. Create two objects and link one as the other's prototype with `Object.create`;
   access an inherited property and confirm with `hasOwnProperty`.
2. Demonstrate shadowing: give a child its own copy of a prototype property.
3. Add a method to a class's `prototype` after creating an instance and show the
   instance can call it.
4. Write a function that walks and prints an object's full prototype chain up to `null`.

---
---

# TIER 4 — OBJECT CREATION PATTERNS

## 8. Creating Objects — Every Approach

JavaScript offers many ways to make objects. Each has trade-offs. Knowing them all
lets you pick the right tool.

### 1. Object Literal

The simplest: write the object directly. Best for one-off objects and config.

```js
const user = {
  name: "Asha",
  greet() { return `Hi, ${this.name}`; },
};
```

Downside: no blueprint — if you need many similar objects, you'd repeat yourself.

### 2. Constructor Function (pre-ES6 class)

A regular function used with `new`. The historical way to make "classes".

```js
function User(name) {
  this.name = name;             // own property per instance
}
User.prototype.greet = function () { // shared method on the prototype
  return `Hi, ${this.name}`;
};

const u = new User("Asha");
console.log(u.greet()); // Hi, Asha
```

`class` is syntax sugar over exactly this.

### 3. `Object.create()`

Creates a new object with an explicitly chosen **prototype**. The purest expression of
prototypal inheritance — no constructor involved.

```js
const proto = {
  greet() { return `Hi, ${this.name}`; },
};

const user2 = Object.create(proto); // prototype is `proto`
user2.name = "Ravi";
console.log(user2.greet()); // Hi, Ravi

// Create a truly empty object with no prototype (no inherited methods):
const bare = Object.create(null);
console.log(bare.toString); // undefined — great for pure dictionaries
```

### 4. Factory Function

A plain function that **returns** an object (no `new`, no `this` headaches). Pairs
naturally with closures for privacy.

```js
function createUser(name) {
  let loginCount = 0; // private via closure

  return {
    name,
    login() { loginCount++; return loginCount; },
  };
}

const u3 = createUser("Asha");
console.log(u3.login()); // 1
console.log(u3.loginCount); // undefined — private
```

**Factory vs constructor:** factories avoid `new` and `this` pitfalls and give easy
privacy; constructors/classes are more memory-efficient (methods shared on prototype)
and support `instanceof`.

### 5. ES6 Class

The modern standard — covered fully in Tier 1. Sugar over constructor functions.

```js
class User4 {
  constructor(name) { this.name = name; }
  greet() { return `Hi, ${this.name}`; }
}
```

### 6. Class Expression

A class assigned to a variable; may be anonymous. Useful for dynamic/returned classes.

```js
const Model = class {
  constructor(data) { this.data = data; }
};
```

### 7. Singleton

A **Singleton** ensures only **one** instance exists, shared everywhere. Good for
things like a single config, logger, or connection pool.

```js
// Simplest: a module-level object is already a singleton.
const config = {
  env: "prod",
  get(key) { return this[key]; },
};

// Class-based singleton that always returns the same instance:
class Database {
  static #instance = null;

  constructor() {
    if (Database.#instance) return Database.#instance; // reuse existing
    this.connectedAt = Date.now();
    Database.#instance = this;
  }
}

const a = new Database();
const b = new Database();
console.log(a === b); // true — same single instance
```

### 8. Computed Property Names (ES6)

Build keys dynamically at creation time.

```js
const field = "email";
const record = {
  id: 1,
  [field]: "a@b.com",         // computed key -> email
  [`is_${field}_valid`]: true, // -> is_email_valid
};
console.log(record.email); // "a@b.com"
```

### Choosing an approach

| Approach | Use when |
|----------|----------|
| Object literal | One-off object, config, data bag |
| `class` | Many similar objects, inheritance, `instanceof` |
| Factory function | Want privacy via closures, avoid `this`/`new` |
| `Object.create` | Need precise prototype control, or a prototype-less map |
| Constructor function | Legacy code, or teaching how `class` works underneath |
| Singleton | Exactly one shared instance needed |

### Exercise 8

1. Create the same `Point` type four ways: literal, class, factory, and `Object.create`.
2. Implement a `Logger` singleton; prove two `new` calls return the same instance.
3. Use `Object.create(null)` to build a safe dictionary and explain why it avoids
   prototype-pollution surprises.

---
---

# TIER 5 — RELATIONSHIPS & COMPOSITION

## 9. Object Relationships & Composition

Objects rarely live alone — they relate to each other. The *kind* of relationship
tells you about ownership and lifecycle. These four are often confused, so each gets
a clear example.

### Association — "uses / knows about"

A general relationship where objects know about each other but neither owns the other.
They have independent lifecycles.

```js
class Teacher {
  constructor(name) { this.name = name; }
}
class Student {
  constructor(name) { this.name = name; }
}

// A teacher is associated with students, but doesn't own them.
const t = new Teacher("Ms. Rao");
const s = new Student("Asha");
// They can reference each other without controlling each other's existence.
```

### Aggregation — "has-a" (shared, independent lifecycle)

A whole-part relationship where parts can **exist independently** of the whole. If the
whole is destroyed, the parts live on.

```js
class Player {
  constructor(name) { this.name = name; }
}
class Team {
  constructor(name) {
    this.name = name;
    this.players = []; // Team HAS players...
  }
  addPlayer(player) { this.players.push(player); }
}

const p1 = new Player("Asha"); // player exists on its own
const team = new Team("Tigers");
team.addPlayer(p1);
// If `team` is deleted, `p1` still exists — aggregation.
```

### Composition — "owns-a" (dependent lifecycle)

A strong whole-part relationship where parts **cannot exist without** the whole. The
whole creates and owns its parts; destroy the whole and the parts go too.

```js
class Engine {
  constructor(hp) { this.hp = hp; }
}
class Car {
  constructor(hp) {
    this.engine = new Engine(hp); // Car CREATES and OWNS its engine
  }
}

const car = new Car(200);
// The engine has no meaning or life outside this car — composition.
```

**Aggregation vs Composition in one line:** aggregation = the part is *passed in* and
survives the whole; composition = the part is *created inside* and dies with the whole.

### Dependency — "depends-on" (temporary use)

The weakest relationship: one object uses another temporarily, usually as a method
parameter. A change to the used class may affect the user.

```js
class Logger {
  log(msg) { console.log(msg); }
}
class OrderService {
  // Depends on a Logger only for the duration of this call.
  placeOrder(order, logger) {
    logger.log(`Order placed: ${order.id}`);
  }
}
```

### Composition Over Inheritance (key principle)

Inheritance creates tight coupling and rigid hierarchies. Often it's better to
**compose** behavior from small pieces than to inherit from a deep class tree.
"Favor composition over inheritance" is one of the most repeated OOP guidelines.

```js
// Instead of a tall hierarchy (Robot extends Machine extends ...),
// compose small capability objects:
const canWalk = (state) => ({
  walk: () => `${state.name} walks`,
});
const canSwim = (state) => ({
  swim: () => `${state.name} swims`,
});

function createDuck(name) {
  const state = { name };
  return { ...state, ...canWalk(state), ...canSwim(state) }; // compose behaviors
}

const duck = createDuck("Donald");
console.log(duck.walk()); // Donald walks
console.log(duck.swim()); // Donald swims
```

### Mixins — reusable behavior shared across classes

A **mixin** packages methods that can be mixed into any class. It's how JS fakes
"multiple inheritance". Two common styles:

```js
// Style 1: Object.assign onto a prototype
const Serializable = {
  toJSON() { return JSON.stringify(this); },
};
const Comparable = {
  equals(other) { return JSON.stringify(this) === JSON.stringify(other); },
};

class Product {
  constructor(name) { this.name = name; }
}
Object.assign(Product.prototype, Serializable, Comparable); // mix in

const prod = new Product("Book");
console.log(prod.toJSON()); // {"name":"Book"}
```

```js
// Style 2: higher-order "class factory" mixins (composable, supports super)
const Timestamped = (Base) => class extends Base {
  stamp() { this.updatedAt = Date.now(); return this; }
};
const Taggable = (Base) => class extends Base {
  addTag(tag) { (this.tags ??= []).push(tag); return this; }
};

class Note {}
class RichNote extends Timestamped(Taggable(Note)) {}

const n = new RichNote();
n.stamp().addTag("urgent");
console.log(n.updatedAt, n.tags); // <timestamp> ["urgent"]
```

### Traits

A **trait** is like a mixin but typically more disciplined: a named, reusable set of
methods meant to be composed, often with conflict-resolution rules. JavaScript has no
built-in traits; they're implemented with the same mixin techniques above. In practice
"trait" and "mixin" are used almost interchangeably in JS.

```js
// A "trait" = a focused, documented capability bundle applied via Object.assign.
const PrintableTrait = {
  print() { return `[${this.constructor.name}] ${this.label}`; },
};
class Ticket { constructor(label) { this.label = label; } }
Object.assign(Ticket.prototype, PrintableTrait);
console.log(new Ticket("A1").print()); // [Ticket] A1
```

### Object Delegation

**Delegation** means an object forwards work to another object it holds, rather than
inheriting. It's composition in action and the runtime basis of the prototype chain.

```js
class Printer {
  print(doc) { return `printing ${doc}`; }
}
class Office {
  constructor() { this.printer = new Printer(); }
  print(doc) { return this.printer.print(doc); } // delegate to the printer
}

console.log(new Office().print("report")); // printing report
```

### Relationship cheat sheet

| Relationship | Meaning | Lifecycle | Example |
|--------------|---------|-----------|---------|
| Association | knows-about | independent | Teacher ↔ Student |
| Aggregation | has-a (shared) | part survives whole | Team has Players |
| Composition | owns-a (exclusive) | part dies with whole | Car owns Engine |
| Dependency | uses temporarily | per method call | Service uses Logger |

### Exercise 9

1. Model a `Library` that aggregates `Book`s (books passed in, survive the library).
2. Model a `House` composed of `Room`s (rooms created inside, owned by the house).
3. Create two mixins (`Loggable`, `Serializable`) and apply both to one class.
4. Rewrite a small inheritance hierarchy using composition instead, and note which
   reads more clearly.

---
---

# TIER 6 — OBJECT & PROPERTY MANIPULATION

## 10. Object Manipulation & Property Descriptors

JavaScript gives fine-grained control over objects and even over individual
properties. This tier covers the built-in `Object.*` tools and the hidden settings
behind every property.

### Enumerating an object

```js
const user = { name: "Asha", age: 25, city: "Mumbai" };

console.log(Object.keys(user));    // ["name", "age", "city"]
console.log(Object.values(user));  // ["Asha", 25, "Mumbai"]
console.log(Object.entries(user)); // [["name","Asha"], ["age",25], ["city","Mumbai"]]

// Iterate key/value pairs cleanly:
for (const [key, value] of Object.entries(user)) {
  console.log(`${key} = ${value}`);
}

// Build an object back from entries:
const copy = Object.fromEntries(Object.entries(user));
```

### `hasOwnProperty` and `Object.hasOwn`

Check for an **own** property (not inherited). `Object.hasOwn` (ES2022) is the safer
modern form.

```js
console.log(user.hasOwnProperty("name")); // true
console.log(Object.hasOwn(user, "name"));  // true (preferred)
```

### `Object.assign` — copy/merge properties

Copies **own enumerable** properties from sources into a target. This is a **shallow**
copy (nested objects are shared, not cloned — see Tier 7).

```js
const defaults = { theme: "light", fontSize: 14 };
const prefs = { fontSize: 18 };

const settings = Object.assign({}, defaults, prefs);
console.log(settings); // { theme: "light", fontSize: 18 } — later sources win
```

Spread `{ ...a, ...b }` does the same thing and is usually preferred for readability.

### Controlling mutability: freeze / seal / preventExtensions

Three levels of locking down an object, from strictest to loosest:

```js
// 1. Object.freeze — no add, no remove, no change (fully immutable, shallow)
const frozen = Object.freeze({ x: 1 });
frozen.x = 99;      // ignored (throws in strict mode)
frozen.y = 2;       // ignored
console.log(frozen); // { x: 1 }
console.log(Object.isFrozen(frozen)); // true

// 2. Object.seal — can CHANGE existing props, but can't add or remove
const sealed = Object.seal({ x: 1 });
sealed.x = 99;      // allowed
sealed.y = 2;       // ignored (can't add)
console.log(sealed); // { x: 99 }
console.log(Object.isSealed(sealed)); // true

// 3. Object.preventExtensions — can change AND delete, but can't add new
const locked = Object.preventExtensions({ x: 1 });
locked.x = 99;      // allowed
delete locked.x;    // allowed
locked.y = 2;       // ignored (can't add)
console.log(Object.isExtensible(locked)); // false
```

| Method | Change existing | Delete | Add new |
|--------|:---:|:---:|:---:|
| `freeze` | ❌ | ❌ | ❌ |
| `seal` | ✅ | ❌ | ❌ |
| `preventExtensions` | ✅ | ✅ | ❌ |

> **Shallow note:** `freeze` only locks the top level. Nested objects stay mutable
> unless you deep-freeze them recursively (shown in Tier 7).

### Property Descriptors

Every property has hidden settings called a **descriptor**. There are two kinds:

- **Data property** — has a `value` plus `writable`, `enumerable`, `configurable`.
- **Accessor property** — has `get`/`set` plus `enumerable`, `configurable`.

```js
const obj = { name: "Asha" };
console.log(Object.getOwnPropertyDescriptor(obj, "name"));
// { value: "Asha", writable: true, enumerable: true, configurable: true }
```

The three attribute flags:

- **`writable`** — can the value be changed with `=`?
- **`enumerable`** — does it show up in `for...in`, `Object.keys`, spread?
- **`configurable`** — can the descriptor be changed or the property deleted?

### `Object.defineProperty` — precise property control

Define a property with exact settings. By default each flag is `false`, which is the
opposite of normal assignment.

```js
const config = {};

Object.defineProperty(config, "API_KEY", {
  value: "secret-123",
  writable: false,     // read-only
  enumerable: false,   // hidden from Object.keys / for...in / spread
  configurable: false, // can't be deleted or redefined
});

console.log(config.API_KEY);    // "secret-123"
config.API_KEY = "new";          // ignored (not writable)
console.log(Object.keys(config)); // [] — not enumerable
```

### `Object.defineProperties` — define several at once

```js
const product = {};
Object.defineProperties(product, {
  name: { value: "Book", enumerable: true, writable: true },
  id:   { value: 1, enumerable: false },  // hidden internal id
});
console.log(Object.keys(product)); // ["name"] — id is hidden
```

### Accessor properties via descriptor

```js
const temp = { celsius: 25 };
Object.defineProperty(temp, "fahrenheit", {
  get() { return this.celsius * 9 / 5 + 32; },
  set(f) { this.celsius = (f - 32) * 5 / 9; },
  enumerable: true,
});
console.log(temp.fahrenheit); // 77
temp.fahrenheit = 212;
console.log(temp.celsius);    // 100
```

### Data Property vs Accessor Property (summary)

- **Data property:** stores a direct value. Flags: `value`, `writable`, `enumerable`,
  `configurable`.
- **Accessor property:** computed via `get`/`set`. Flags: `get`, `set`, `enumerable`,
  `configurable` (no `value`/`writable`).

### Destructuring, Spread & Rest with objects (recap in OOP context)

```js
const { name, ...rest } = user;   // rest = everything except name
const merged = { ...defaults, ...prefs }; // spread merge (shallow)
```

### Exercise 10

1. Use `Object.entries` to print all key/value pairs of an object.
2. Freeze an object and prove in strict mode that assignment throws.
3. Use `defineProperty` to add a hidden, read-only `createdAt` timestamp that doesn't
   appear in `Object.keys`.
4. Define an accessor property `fullName` from `firstName` and `lastName`.

---
---

# TIER 7 — CONTEXT, BINDING & IMMUTABILITY

## 11. this, Binding, Cloning & Immutability

`this` is the most misunderstood keyword in JavaScript. Its value is decided by **how
a function is called**, not where it's defined. There are four binding rules.

### The `this` keyword — what it points to

```js
// `this` depends entirely on the call-site.
function show() { return this; }
```

### Rule 1 — Default Binding

A plain function call. `this` is the global object (`window`/`globalThis`) in sloppy
mode, or `undefined` in **strict mode** (and inside modules, which are always strict).

```js
"use strict";
function f() { return this; }
console.log(f()); // undefined (strict mode)
```

### Rule 2 — Implicit Binding

When called as a method, `this` is the object **left of the dot**.

```js
const user = {
  name: "Asha",
  greet() { return this.name; },
};
console.log(user.greet()); // "Asha" — `this` is `user`

// Lost binding — the classic bug:
const fn = user.greet;
console.log(fn()); // undefined — no object left of the dot anymore
```

### Rule 3 — Explicit Binding: `call`, `apply`, `bind`

You can force `this` explicitly.

```js
function introduce(greeting, punctuation) {
  return `${greeting}, I'm ${this.name}${punctuation}`;
}
const person = { name: "Asha" };

// call — pass args individually
console.log(introduce.call(person, "Hi", "!"));   // Hi, I'm Asha!

// apply — pass args as an array
console.log(introduce.apply(person, ["Hey", "."])); // Hey, I'm Asha.

// bind — returns a NEW function with `this` permanently fixed
const bound = introduce.bind(person, "Hello");
console.log(bound("?")); // Hello, I'm Asha?
```

- **`call(thisArg, ...args)`** — invoke now, args listed.
- **`apply(thisArg, [args])`** — invoke now, args in an array.
- **`bind(thisArg, ...args)`** — don't invoke; return a bound copy for later.

### Rule 4 — `new` Binding

Using `new`, `this` is the brand-new instance (see Tier 3's `[[Construct]]`).

```js
function User(name) { this.name = name; }
const u = new User("Asha"); // `this` is the new object
```

### Arrow Functions and `this` — Lexical Binding

Arrow functions **don't have their own `this`**. They capture `this` from the
surrounding (lexical) scope at definition time. This solves the "lost binding" bug in
callbacks.

```js
class Timer {
  constructor() { this.seconds = 0; }

  start() {
    setInterval(() => {
      this.seconds++;          // arrow keeps `this` = the Timer instance
      console.log(this.seconds);
    }, 1000);
  }
}
// A regular function here would make `this` undefined/global — a common bug.
```

Arrow functions ignore `call`/`apply`/`bind` for `this` — their `this` is fixed.

### Binding priority (highest to lowest)

1. `new` binding
2. Explicit binding (`call`/`apply`/`bind`)
3. Implicit binding (method call)
4. Default binding (plain call)

Arrow functions sit outside this entirely — they use lexical `this`.

---

### Cloning & Immutability

Because objects are reference types (Tier 1), copying needs care.

### Shallow Copy

Copies the top level only; nested objects are **shared** (same reference).

```js
const original = { name: "Asha", address: { city: "Mumbai" } };

const shallow = { ...original };          // or Object.assign({}, original)
shallow.name = "Ravi";                     // top-level change — safe
shallow.address.city = "Delhi";            // mutates the SHARED nested object!

console.log(original.name);         // "Asha"  (unaffected)
console.log(original.address.city); // "Delhi" (changed! shared reference)
```

### Deep Copy

Clones every level, so nothing is shared.

```js
const original = { name: "Asha", address: { city: "Mumbai" } };

// Modern built-in (best for most cases): structuredClone (ES2021/Node 17+)
const deep = structuredClone(original);
deep.address.city = "Delhi";
console.log(original.address.city); // "Mumbai" — fully independent

// Older JSON trick (loses functions, dates, undefined, Maps, etc.):
const deep2 = JSON.parse(JSON.stringify(original));
```

> `structuredClone` is the recommended deep-copy today. The JSON trick is a quick
> fallback but drops anything not representable in JSON (functions, `undefined`,
> `Date` becomes a string, `Map`/`Set` are lost).

### Mutable vs Immutable Objects

- **Mutable** — can be changed after creation (the default for objects/arrays).
- **Immutable** — cannot change; any "change" produces a new object. Immutability makes
  code predictable and is central to React/Redux-style state.

```js
// Immutable update pattern — never mutate, always create a new object:
const state = { count: 1, user: { name: "Asha" } };
const nextState = { ...state, count: state.count + 1 };
console.log(state.count);     // 1 (original untouched)
console.log(nextState.count); // 2
```

### Deep Freeze — enforcing immutability all the way down

`Object.freeze` is shallow (Tier 6). To make a nested object truly immutable, freeze
recursively.

```js
function deepFreeze(obj) {
  Object.keys(obj).forEach((key) => {
    const value = obj[key];
    if (value && typeof value === "object") deepFreeze(value); // recurse
  });
  return Object.freeze(obj);
}

const config = deepFreeze({ api: { url: "x", retries: 3 } });
config.api.url = "y"; // ignored (throws in strict mode)
console.log(config.api.url); // "x"
```

### Exercise 11

1. Create an object method, assign it to a bare variable, call it, and observe the
   lost-`this` bug. Fix it with `bind`.
2. Use `call` and `apply` to borrow one object's method for another object.
3. Show the shallow-copy nested-mutation bug, then fix it with `structuredClone`.
4. Write `deepFreeze` and prove a nested property can't be changed.
5. Implement an immutable "update" that returns a new object with one changed field.

---
---

# TIER 8 — METAPROGRAMMING & REFLECTION

## 12. Reflection & Metaprogramming

**Metaprogramming** is code that inspects or changes other code/objects at runtime.
**Reflection** is inspecting and modifying an object's structure programmatically.
JavaScript provides three main tools: `Symbol`, `Reflect`, and `Proxy`.

### Symbols — unique, hidden keys

A **`Symbol`** is a guaranteed-unique primitive, often used as a property key that
won't collide with others and won't appear in normal enumeration.

```js
const id = Symbol("id"); // description is just a label, not an identity
const user = { name: "Asha", [id]: 123 };

console.log(user[id]);        // 123
console.log(Object.keys(user)); // ["name"] — the symbol key is hidden
console.log(Symbol("x") === Symbol("x")); // false — always unique
```

### Symbol registry (shared symbols)

```js
const a = Symbol.for("app.id"); // creates or reuses a global symbol
const b = Symbol.for("app.id");
console.log(a === b); // true — same registered symbol
```

### Well-known Symbols — hook into language behavior

Certain built-in symbols let your objects customize how the language treats them.

```js
// Symbol.iterator — make an object iterable with for...of and spread
class Range {
  constructor(start, end) { this.start = start; this.end = end; }
  [Symbol.iterator]() {
    let current = this.start;
    const end = this.end;
    return {
      next() {
        return current <= end
          ? { value: current++, done: false }
          : { value: undefined, done: true };
      },
    };
  }
}
console.log([...new Range(1, 4)]); // [1, 2, 3, 4]

// Symbol.toPrimitive — control coercion to number/string
class Money {
  constructor(amount) { this.amount = amount; }
  [Symbol.toPrimitive](hint) {
    return hint === "string" ? `$${this.amount}` : this.amount;
  }
}
const m = new Money(50);
console.log(`${m}`); // "$50"  (string hint)
console.log(m * 2);  // 100    (number hint)

// Symbol.toStringTag — customize Object.prototype.toString
class Widget {
  get [Symbol.toStringTag]() { return "Widget"; }
}
console.log(Object.prototype.toString.call(new Widget())); // [object Widget]

// Symbol.hasInstance — customize instanceof
class Even {
  static [Symbol.hasInstance](value) { return value % 2 === 0; }
}
console.log(4 instanceof Even); // true
console.log(3 instanceof Even); // false

// Symbol.species — control which constructor derived methods use (advanced)
```

### `Reflect` — a clean API for object operations

The **`Reflect`** object provides function versions of internal operations (get, set,
delete, etc.). It's cleaner than the older operators and pairs perfectly with `Proxy`.

```js
const obj = { x: 1 };

Reflect.get(obj, "x");           // 1
Reflect.set(obj, "y", 2);         // true  (obj.y = 2)
Reflect.has(obj, "x");            // true  (like the `in` operator)
Reflect.deleteProperty(obj, "x"); // true
Reflect.ownKeys(obj);             // ["y"] (all keys incl. symbols)

// Construct and apply reflectively:
class P { constructor(n) { this.n = n; } }
const p = Reflect.construct(P, [5]);     // like new P(5)
Reflect.apply(Math.max, null, [1, 9, 3]); // 9
```

### `Proxy` — intercept operations with traps

A **`Proxy`** wraps an object and lets you intercept fundamental operations via
**traps** (handler functions). This powers validation, logging, reactive frameworks
(Vue 3), and more.

```js
const target = { name: "Asha", age: 25 };

const handler = {
  get(obj, prop, receiver) {
    console.log(`reading ${String(prop)}`);
    return Reflect.get(obj, prop, receiver); // delegate to default behavior
  },
  set(obj, prop, value, receiver) {
    if (prop === "age" && typeof value !== "number") {
      throw new TypeError("age must be a number"); // validation trap
    }
    return Reflect.set(obj, prop, value, receiver);
  },
};

const proxy = new Proxy(target, handler);
proxy.name;        // logs "reading name" -> "Asha"
proxy.age = 30;    // allowed
// proxy.age = "x"; // throws TypeError
```

### Common Proxy traps

| Trap | Intercepts |
|------|-----------|
| `get` | property read |
| `set` | property write |
| `has` | the `in` operator |
| `deleteProperty` | `delete obj.x` |
| `ownKeys` | `Object.keys`, `for...in` |
| `apply` | calling a function |
| `construct` | `new` on a function |
| `defineProperty` | `Object.defineProperty` |
| `getPrototypeOf` | `Object.getPrototypeOf` |

### Dynamic Property & Method Creation

Metaprogramming often means building members at runtime.

```js
// Dynamic properties
const obj2 = {};
["x", "y", "z"].forEach((key, i) => { obj2[key] = i; });
console.log(obj2); // { x: 0, y: 1, z: 2 }

// Dynamic methods on a class prototype
class Api {}
["get", "post", "put", "delete"].forEach((verb) => {
  Api.prototype[verb] = function (url) {
    return `${verb.toUpperCase()} ${url}`;
  };
});
const api = new Api();
console.log(api.post("/users")); // "POST /users"

// A Proxy that generates methods on the fly:
const dynamic = new Proxy({}, {
  get(_, prop) {
    return (...args) => `called ${String(prop)} with [${args}]`;
  },
});
console.log(dynamic.anything(1, 2)); // "called anything with [1,2]"
```

### Exercise 12

1. Add `Symbol.iterator` to a class so `for...of` works over its internal data.
2. Build a validating `Proxy` that rejects negative numbers assigned to any property.
3. Use `Reflect.ownKeys` to list a mix of string and symbol keys on an object.
4. Create a Proxy that logs every property access and delegates with `Reflect`.

---
---

# TIER 9 — PRINCIPLES

## 13. SOLID, GRASP & Architectural Principles

Principles are the guidelines that keep larger OOP codebases maintainable. They're not
rules to apply blindly — they're trade-offs to reach for when complexity grows.

### The SOLID Principles

Five principles for building flexible, maintainable object-oriented code.

#### S — Single Responsibility Principle (SRP)

A class should have **one reason to change** — one job.

```js
// ❌ Does too much: user data AND persistence AND emailing.
class UserBad {
  save() {}
  sendEmail() {}
}

// ✅ Split responsibilities.
class User { constructor(name) { this.name = name; } }
class UserRepository { save(user) { /* persistence only */ } }
class EmailService { send(user, msg) { /* email only */ } }
```

#### O — Open/Closed Principle (OCP)

Open for **extension**, closed for **modification**. Add behavior without editing
existing, tested code.

```js
// ✅ Add new shapes without touching AreaCalculator.
class AreaCalculator {
  area(shape) { return shape.area(); } // relies on a shared method
}
class Circle { constructor(r) { this.r = r; } area() { return Math.PI * this.r ** 2; } }
class Square { constructor(s) { this.s = s; } area() { return this.s ** 2; } }
// New shape = new class with area(); calculator stays unchanged.
```

#### L — Liskov Substitution Principle (LSP)

A subclass must be usable **anywhere its parent is**, without breaking behavior.

```js
// ❌ Classic violation: Square breaks Rectangle's width/height contract.
// ✅ Subtypes should honor the parent's expectations.
class Bird { }
class FlyingBird extends Bird { fly() {} }
class Penguin extends Bird { /* no fly() — doesn't pretend to */ }
// Don't give Penguin a fly() that throws; model the hierarchy honestly.
```

#### I — Interface Segregation Principle (ISP)

Don't force a class to depend on methods it doesn't use. Prefer small, focused
"interfaces" (in JS, small capability objects/mixins) over one fat one.

```js
// ✅ Small capabilities instead of one giant interface.
const Printer = { print() {} };
const Scanner = { scan() {} };
// A simple printer gets only Printer; a combo device gets both.
```

#### D — Dependency Inversion Principle (DIP)

Depend on **abstractions**, not concrete implementations. High-level code shouldn't
hard-wire low-level details.

```js
// ✅ Inject a dependency that satisfies an expected shape.
class NotificationService {
  constructor(sender) { this.sender = sender; } // depends on an abstraction
  notify(msg) { this.sender.send(msg); }
}
class EmailSender { send(msg) { /* ... */ } }
class SmsSender { send(msg) { /* ... */ } }

new NotificationService(new EmailSender()).notify("hi"); // swap senders freely
```

> This leads directly to **Dependency Injection** (Tier 11): pass dependencies in
> rather than creating them inside.

### Cohesion & Coupling

- **Cohesion** — how focused a module is. **High cohesion** (everything in a class
  belongs together) is good.
- **Coupling** — how dependent modules are on each other. **Low (loose) coupling** is
  good; changes in one place shouldn't ripple everywhere.

Aim for **high cohesion, low coupling**. SOLID largely serves this goal.

### Separation of Concerns (SoC)

Split a system into distinct parts, each addressing one concern (e.g., data access,
business logic, presentation). Layers and modules enforce this.

### DRY — Don't Repeat Yourself

Every piece of knowledge should have one authoritative place. Duplicate logic becomes
duplicate bugs.

```js
// ❌ Repeated tax logic in many places.
// ✅ One function, reused everywhere.
function withTax(price) { return price * 1.18; }
```

### KISS — Keep It Simple

Prefer the simplest solution that works. Clever code is a maintenance cost.

### YAGNI — You Aren't Gonna Need It

Don't build features or abstractions "just in case". Add them when a real need appears.

### Law of Demeter (Principle of Least Knowledge)

An object should only talk to its **immediate** collaborators — avoid long chains that
reach deep into other objects' internals ("don't talk to strangers").

```js
// ❌ Reaches through several objects — fragile.
order.getCustomer().getAddress().getCity();

// ✅ Ask the direct collaborator for what you need.
order.getShippingCity();
```

### GRASP Principles (brief)

**GRASP** = General Responsibility Assignment Software Patterns — guidance on *who*
should own a responsibility:

- **Information Expert** — give a responsibility to the class that has the data for it.
- **Creator** — the class that aggregates/contains B should create B.
- **Controller** — a dedicated object coordinates a use case.
- **Low Coupling / High Cohesion** — the overarching goals (above).
- **Polymorphism** — use it instead of type-checking conditionals.
- **Pure Fabrication** — invent a helper class (e.g., a Repository) when no domain
  class fits, to keep cohesion high.
- **Indirection** — introduce an intermediary to decouple two parts.
- **Protected Variations** — wrap unstable parts behind a stable interface.

### Exercise 13

1. Take a class that both stores data and saves to a database; split it per SRP.
2. Refactor an `if (type === ...)` chain into polymorphism (OCP + GRASP polymorphism).
3. Rewrite a Law-of-Demeter-violating chain by adding a method to the direct object.
4. Identify one place in prior exercises where DRY or DIP would improve the design.

---
---

# TIER 10 — DESIGN PATTERNS

## 14. Design Patterns

**Design patterns** are proven, reusable solutions to recurring design problems. They
fall into three families: **creational** (how objects are made), **structural** (how
objects are composed), and **behavioral** (how objects interact). Each below has a
one-line intent and a compact JS example.

---

### CREATIONAL PATTERNS

#### Singleton — one shared instance

```js
class AppConfig {
  static #instance;
  constructor() {
    if (AppConfig.#instance) return AppConfig.#instance;
    this.settings = {};
    AppConfig.#instance = this;
  }
}
console.log(new AppConfig() === new AppConfig()); // true
```

#### Factory — a method decides which object to create

```js
class Dog { speak() { return "Woof"; } }
class Cat { speak() { return "Meow"; } }

class AnimalFactory {
  static create(type) {
    if (type === "dog") return new Dog();
    if (type === "cat") return new Cat();
    throw new Error("Unknown type");
  }
}
console.log(AnimalFactory.create("dog").speak()); // Woof
```

#### Abstract Factory — a factory of related factories

```js
// Produces families of related objects (e.g., UI kits per theme).
class LightButton { render() { return "light button"; } }
class DarkButton { render() { return "dark button"; } }

class LightUIFactory { createButton() { return new LightButton(); } }
class DarkUIFactory { createButton() { return new DarkButton(); } }

function getUIFactory(theme) {
  return theme === "dark" ? new DarkUIFactory() : new LightUIFactory();
}
console.log(getUIFactory("dark").createButton().render()); // dark button
```

#### Builder — construct complex objects step by step

```js
class Burger {
  constructor() { this.parts = []; }
}
class BurgerBuilder {
  constructor() { this.burger = new Burger(); }
  add(part) { this.burger.parts.push(part); return this; } // chainable
  build() { return this.burger; }
}
const burger = new BurgerBuilder().add("bun").add("patty").add("cheese").build();
console.log(burger.parts); // ["bun", "patty", "cheese"]
```

#### Prototype — clone an existing object

```js
const prototypeCar = {
  wheels: 4,
  clone() { return structuredClone(this); },
};
const car = prototypeCar.clone();
car.wheels = 6;
console.log(prototypeCar.wheels, car.wheels); // 4 6
```

---

### STRUCTURAL PATTERNS

#### Adapter — make an incompatible interface fit

```js
// Old API returns {temp_f}; our app expects getCelsius().
class FahrenheitSensor { readF() { return 212; } }

class CelsiusAdapter {
  constructor(sensor) { this.sensor = sensor; }
  getCelsius() { return (this.sensor.readF() - 32) * 5 / 9; }
}
console.log(new CelsiusAdapter(new FahrenheitSensor()).getCelsius()); // 100
```

#### Facade — a simple front over a complex subsystem

```js
class CPU { freeze() {} jump() {} execute() {} }
class Memory { load() {} }
class ComputerFacade {
  constructor() { this.cpu = new CPU(); this.memory = new Memory(); }
  start() { this.cpu.freeze(); this.memory.load(); this.cpu.jump(); this.cpu.execute(); }
}
new ComputerFacade().start(); // one simple call hides the complexity
```

#### Decorator — add behavior by wrapping

```js
function withLogging(fn) {
  return function (...args) {
    console.log(`calling with ${args}`);
    return fn(...args);
  };
}
const add = (a, b) => a + b;
const loggedAdd = withLogging(add);
loggedAdd(2, 3); // logs, then returns 5
```

#### Proxy — a stand-in that controls access

```js
const service = { fetchData: () => "data" };
const cachingProxy = new Proxy(service, {
  get(target, prop) {
    if (prop === "fetchData") {
      let cache;
      return () => (cache ??= target.fetchData()); // cache the result
    }
    return target[prop];
  },
});
```

#### Composition note — Bridge, Composite, Flyweight

- **Bridge** — separate an abstraction from its implementation so they vary
  independently (e.g., `Shape` holding a `Renderer`).
- **Composite** — treat individual objects and groups uniformly (a tree of nodes with
  the same interface, like a file-system folder containing files and folders).
- **Flyweight** — share common state across many objects to save memory.

```js
// Composite sketch:
class FileNode { constructor(size) { this.size = size; } getSize() { return this.size; } }
class Folder {
  constructor() { this.children = []; }
  add(node) { this.children.push(node); return this; }
  getSize() { return this.children.reduce((t, c) => t + c.getSize(), 0); }
}
console.log(new Folder().add(new FileNode(10)).add(new FileNode(5)).getSize()); // 15
```

---

### BEHAVIORAL PATTERNS

#### Observer — subscribers react to a subject's changes

```js
class Subject {
  #observers = [];
  subscribe(fn) { this.#observers.push(fn); }
  notify(data) { this.#observers.forEach((fn) => fn(data)); }
}
const news = new Subject();
news.subscribe((headline) => console.log("Reader 1:", headline));
news.notify("Breaking news!"); // Reader 1: Breaking news!
```

#### Strategy — swap interchangeable algorithms

```js
const strategies = {
  add: (a, b) => a + b,
  multiply: (a, b) => a * b,
};
class Calculator {
  constructor(strategy) { this.strategy = strategy; }
  execute(a, b) { return this.strategy(a, b); }
}
console.log(new Calculator(strategies.multiply).execute(3, 4)); // 12
```

#### Command — wrap an action as an object (supports undo/queue)

```js
class AddCommand {
  constructor(receiver, value) { this.receiver = receiver; this.value = value; }
  execute() { this.receiver.total += this.value; }
  undo() { this.receiver.total -= this.value; }
}
const account = { total: 0 };
const cmd = new AddCommand(account, 50);
cmd.execute(); console.log(account.total); // 50
cmd.undo();    console.log(account.total); // 0
```

#### State — behavior changes with internal state

```js
class TrafficLight {
  constructor() { this.state = "red"; }
  next() {
    const transitions = { red: "green", green: "yellow", yellow: "red" };
    this.state = transitions[this.state];
    return this.state;
  }
}
const light = new TrafficLight();
console.log(light.next(), light.next()); // green yellow
```

#### Mediator — centralize communication between objects

```js
class ChatRoom {
  showMessage(user, message) { return `[${user}]: ${message}`; }
}
class ChatUser {
  constructor(name, mediator) { this.name = name; this.mediator = mediator; }
  send(msg) { return this.mediator.showMessage(this.name, msg); }
}
const room = new ChatRoom();
console.log(new ChatUser("Asha", room).send("hi")); // [Asha]: hi
```

#### Chain of Responsibility — pass a request along handlers

```js
class Handler {
  setNext(h) { this.next = h; return h; }
  handle(req) { return this.next ? this.next.handle(req) : null; }
}
class AuthHandler extends Handler {
  handle(req) { return req.user ? super.handle(req) : "rejected: no user"; }
}
class LogHandler extends Handler {
  handle(req) { console.log("logging"); return super.handle(req); }
}
const chain = new AuthHandler();
chain.setNext(new LogHandler());
console.log(chain.handle({ user: null })); // rejected: no user
```

#### Template Method — fixed skeleton, overridable steps

```js
class DataProcessor {
  process() { return this.read() + "->" + this.transform(); } // skeleton
  read() { return "raw"; }
  transform() { throw new Error("implement transform()"); } // step to override
}
class UpperProcessor extends DataProcessor {
  transform() { return "TRANSFORMED"; }
}
console.log(new UpperProcessor().process()); // raw->TRANSFORMED
```

#### Dependency Injection — supply dependencies from outside

```js
class Service {
  constructor(logger) { this.logger = logger; } // injected, not created inside
  run() { this.logger.log("running"); }
}
new Service({ log: (m) => console.log(m) }).run(); // running
```

(More on DI containers in Tier 11.)

### Pattern family cheat sheet

| Family | Patterns |
|--------|----------|
| Creational | Singleton, Factory, Abstract Factory, Builder, Prototype |
| Structural | Adapter, Facade, Decorator, Proxy, Bridge, Composite, Flyweight |
| Behavioral | Observer, Strategy, Command, State, Mediator, Chain of Responsibility, Template Method |

### Exercise 14

1. Build a `ShapeFactory` that creates circles, squares, and triangles.
2. Implement an Observer-based event system with `subscribe` / `unsubscribe` / `notify`.
3. Use the Strategy pattern to switch between sort algorithms at runtime.
4. Implement a Command with `undo`, and a small history stack to undo multiple commands.

---
---

# TIER 11 — ENTERPRISE / ARCHITECT

## 15. Enterprise, DDD & Event-Driven Design

The highest tier: how objects are organized in large, long-lived applications. These
are architectural concepts — learn them after you've built real systems, since they
solve problems that only appear at scale.

### JavaScript-Specific OOP building blocks (foundation for this tier)

Before the patterns, a few JS features that enterprise code leans on:

```js
// First-class functions — functions are values (pass, return, store)
const ops = [(x) => x + 1, (x) => x * 2];

// Higher-order functions — take/return functions
const compose = (f, g) => (x) => f(g(x));

// Closures — private state (Tier 2) underpin modules & DI

// Modules (ES6) — the real unit of encapsulation in modern JS
// file: mathUtils.js
export function add(a, b) { return a + b; }   // export
export default class Calculator {}
// file: app.js
// import Calculator, { add } from "./mathUtils.js";

// Module Pattern (pre-ESM, via IIFE + closure)
const Counter = (function () {
  let count = 0;                 // private
  return { inc() { return ++count; } }; // public API
})();

// Revealing Module Pattern — define privately, "reveal" chosen members
const Store = (function () {
  let data = {};
  function set(k, v) { data[k] = v; }
  function get(k) { return data[k]; }
  return { set, get }; // reveal
})();

// Namespacing — group related code under one object (pre-module technique)
const App = App || {};
App.utils = { formatDate() {} };
```

### Domain-Driven Design (DDD) — modeling the business

DDD organizes code around the **business domain**. Its core building blocks:

#### Entity — identity that persists over time

An **entity** is defined by a unique identity, not its attributes. Two users with the
same name are different if their IDs differ.

```js
class User {
  constructor(id, name) {
    this.id = id;     // identity — what makes it unique
    this.name = name; // attributes can change; identity doesn't
  }
  equals(other) { return other instanceof User && this.id === other.id; }
}
```

#### Value Object — defined by its values, immutable, no identity

A **value object** has no identity; two with the same values are equal. Make them
immutable.

```js
class Money {
  constructor(amount, currency) {
    this.amount = amount;
    this.currency = currency;
    Object.freeze(this); // immutable
  }
  equals(other) { return this.amount === other.amount && this.currency === other.currency; }
  add(other) { return new Money(this.amount + other.amount, this.currency); } // returns new
}
```

#### Aggregate & Aggregate Root — a consistency boundary

An **aggregate** is a cluster of related objects treated as one unit. The **aggregate
root** is the single entry point; outside code only touches the root, which keeps the
whole group consistent.

```js
class Order {           // Aggregate Root
  #items = [];          // internal entities — not exposed directly
  addItem(product, qty) {
    this.#items.push({ product, qty }); // all changes go through the root
  }
  get total() {
    return this.#items.reduce((t, i) => t + i.product.price * i.qty, 0);
  }
}
```

#### Repository — abstracts persistence

A **repository** gives a collection-like interface for loading/saving aggregates,
hiding the database behind domain terms.

```js
class UserRepository {
  #store = new Map();
  save(user) { this.#store.set(user.id, user); }
  findById(id) { return this.#store.get(id) ?? null; }
  findAll() { return [...this.#store.values()]; }
}
```

#### Domain Service — logic that doesn't belong to one entity

When behavior spans multiple entities, put it in a **domain service** rather than
forcing it onto one object.

```js
class TransferService {
  transfer(fromAccount, toAccount, amount) {
    fromAccount.withdraw(amount);
    toAccount.deposit(amount);
  }
}
```

#### Factory & Specification (DDD)

- **Factory** — encapsulates complex aggregate creation (Tier 10 factory, applied to
  domain objects).
- **Specification** — encapsulates a business rule as an object you can combine.

```js
class Specification {
  isSatisfiedBy(candidate) { return true; }
  and(other) {
    return { isSatisfiedBy: (c) => this.isSatisfiedBy(c) && other.isSatisfiedBy(c) };
  }
}
class PremiumUserSpec extends Specification {
  isSatisfiedBy(user) { return user.plan === "premium"; }
}
```

### Enterprise Object Types

#### Data Transfer Object (DTO) — a plain data carrier

A **DTO** moves data across boundaries (API ↔ client). No behavior, just fields.

```js
class UserDTO {
  constructor(user) {
    this.id = user.id;
    this.name = user.name;
    // deliberately omit sensitive fields like password
  }
}
```

#### Rich vs Anemic Domain Model

- **Rich domain model** — objects contain both data *and* the behavior that acts on
  it (preferred in DDD).
- **Anemic domain model** — objects are just data bags; logic lives elsewhere in
  services. Common, but considered an anti-pattern in strict DDD because it scatters
  rules.

```js
// Anemic: data only
class AccountAnemic { constructor() { this.balance = 0; } }
// Rich: data + behavior that protects invariants
class Account {
  #balance = 0;
  withdraw(amt) { if (amt > this.#balance) throw new Error("insufficient"); this.#balance -= amt; }
}
```

### Architectural Patterns

#### Service Layer — coordinates use cases

Sits between controllers and the domain, orchestrating repositories and domain
objects for a complete operation.

```js
class UserService {
  constructor(userRepo) { this.userRepo = userRepo; } // DI
  register(name) {
    const user = new User(Date.now(), name);
    this.userRepo.save(user);
    return new UserDTO(user);
  }
}
```

#### Dependency Injection Container

A **DI container** centralizes creation and wiring of dependencies, so classes
receive what they need instead of constructing it.

```js
class Container {
  #services = new Map();
  register(name, factory) { this.#services.set(name, factory); }
  resolve(name) { return this.#services.get(name)(this); } // pass container for deps
}

const container = new Container();
container.register("userRepo", () => new UserRepository());
container.register("userService", (c) => new UserService(c.resolve("userRepo")));

const service = container.resolve("userService");
```

#### CQRS — separate reads from writes

**Command Query Responsibility Segregation**: commands (change state) and queries
(read state) use separate models/paths, which scales and clarifies large systems.

```js
// Command side — changes state, returns nothing meaningful
class CreateUserCommand { constructor(name) { this.name = name; } }
class UserCommandHandler {
  constructor(repo) { this.repo = repo; }
  handle(cmd) { this.repo.save(new User(Date.now(), cmd.name)); }
}
// Query side — reads only, optimized for display
class UserQueryHandler {
  constructor(repo) { this.repo = repo; }
  getAll() { return this.repo.findAll().map((u) => new UserDTO(u)); }
}
```

### Event-Driven Object Design

#### Observer Lifecycle & Publish-Subscribe

**Pub/Sub** decouples senders from receivers through named channels/events. (Observer,
Tier 10, is the direct-coupling cousin; pub/sub adds a broker in the middle.)

```js
class EventBus {
  #listeners = new Map();
  on(event, cb) {
    if (!this.#listeners.has(event)) this.#listeners.set(event, []);
    this.#listeners.get(event).push(cb);
  }
  off(event, cb) {
    const arr = this.#listeners.get(event) ?? [];
    this.#listeners.set(event, arr.filter((f) => f !== cb)); // unsubscribe = lifecycle
  }
  emit(event, data) { (this.#listeners.get(event) ?? []).forEach((cb) => cb(data)); }
}

const bus = new EventBus();
const handler = (u) => console.log("user created:", u.name);
bus.on("user.created", handler);
bus.emit("user.created", { name: "Asha" }); // user created: Asha
bus.off("user.created", handler);           // lifecycle: unsubscribe
```

#### Event Emitter Pattern

Node.js formalizes this with `EventEmitter`. The pattern: objects emit named events;
others listen. It's the backbone of event-driven architecture.

```js
// Node.js:
// import { EventEmitter } from "events";
// class Order extends EventEmitter { place() { this.emit("placed", this); } }
```

#### Command & Callback Objects

- **Command objects** (Tier 10) — actions as objects, queued or logged for event
  sourcing.
- **Callback objects** — objects passed in to be invoked on an event (a handler bundle).

### Exercise 15

1. Model an `Order` aggregate root with private `#items`; expose only `addItem`/`total`.
2. Build a `UserRepository` with an in-memory `Map` and `save`/`findById`/`findAll`.
3. Implement a tiny DI container that wires a service to its repository.
4. Build an `EventBus` with `on`/`off`/`emit`; show subscribe and unsubscribe working.
5. Create a `Money` value object (immutable, value equality) and prove two equal-valued
   instances are `equals()` but not `===`.

---
---

## Final Wrap-Up

You've now covered the full OOP landscape in JavaScript, from objects and classes to
prototypes, patterns, principles, and enterprise architecture.

### Recommended learning path

1. **Freshers:** master Tiers 1–4. Build small class-based programs until they feel natural.
2. **Intermediate:** Tiers 5–7 (relationships, object/property control, `this`/immutability).
3. **Advanced:** Tier 8 (metaprogramming) and Tier 9 (principles) once you're reading
   and writing real codebases.
4. **Architect:** Tiers 10–11 (patterns, DDD, event-driven) when designing larger systems.

### Honest reminders

- **Don't over-engineer.** Most code needs Tiers 1–7. Reach for patterns and DDD only
  when real complexity justifies them (remember YAGNI/KISS from Tier 9).
- **JS is prototype-based.** `class` is sugar; the prototype system (Tier 3) is the truth.
- **Some "OOP keywords" are patterns in JS**, not language features (`interface`,
  `abstract`, `protected`). TypeScript adds compile-time versions if you need them.
- **Favor composition over inheritance** when a hierarchy starts feeling forced.

### Companion files

- `javascript-from-scratch.md` — core language fundamentals (start here).
- `javascript-oop-complete.md` — this guide.

Happy architecting!

---
---

# APPENDIX — GAP-FILLERS

Full, runnable coverage for the few items earlier tiers only mentioned briefly, plus
one that was missing. Read these alongside the tier they belong to.

## A1. WeakSet (belongs with Tier 8 / Tier 2)

A **`WeakSet`** holds a collection of **objects only**, held *weakly* — if an object
has no other references, it can be garbage-collected and drops out of the set
automatically. It's not iterable and has no `size`. Great for tagging objects without
preventing their cleanup or leaking memory.

```js
const processed = new WeakSet();

function handle(task) {
  if (processed.has(task)) return "already handled";
  processed.add(task);
  return "handled";
}

let task = { id: 1 };
console.log(handle(task)); // "handled"
console.log(handle(task)); // "already handled"

// WeakSet only accepts objects:
// processed.add(1); // TypeError — primitives not allowed

// Common OOP use: track which instances passed a validation/initialization step,
// without keeping them alive just for the bookkeeping.
```

**`WeakSet` vs `Set`:** `Set` holds any value and keeps strong references (prevents
GC, is iterable, has `size`). `WeakSet` holds only objects, weakly, and is not
iterable — use it purely for presence checks tied to object lifetime.

## A2. Bridge Pattern (belongs with Tier 10 — Structural)

**Bridge** separates an **abstraction** from its **implementation** so the two can
vary independently. Instead of a combinatorial explosion of subclasses
(`RedCircle`, `BlueCircle`, `RedSquare`...), you compose a shape with a renderer.

```js
// Implementation side — interchangeable "how to draw"
class VectorRenderer {
  render(shape) { return `drawing ${shape} as vectors`; }
}
class RasterRenderer {
  render(shape) { return `drawing ${shape} as pixels`; }
}

// Abstraction side — holds a reference to an implementation (the "bridge")
class Shape {
  constructor(renderer) { this.renderer = renderer; }
  draw() { throw new Error("subclass implements draw()"); }
}
class Circle extends Shape {
  draw() { return this.renderer.render("circle"); }
}

console.log(new Circle(new VectorRenderer()).draw()); // drawing circle as vectors
console.log(new Circle(new RasterRenderer()).draw()); // drawing circle as pixels
// Add a new shape OR a new renderer independently — no subclass explosion.
```

## A3. Flyweight Pattern (belongs with Tier 10 — Structural)

**Flyweight** saves memory by **sharing** the common (intrinsic) parts of many similar
objects, keeping only the unique (extrinsic) parts separate. Classic for thousands of
particles, map tiles, or text characters.

```js
// Shared intrinsic state is cached and reused across many objects.
class TreeType {
  constructor(name, color) { this.name = name; this.color = color; }
}

class TreeTypeFactory {
  static #types = new Map();
  static get(name, color) {
    const key = `${name}_${color}`;
    if (!this.#types.has(key)) this.#types.set(key, new TreeType(name, color));
    return this.#types.get(key); // same instance reused
  }
}

// Extrinsic state (position) stays per-tree; the type is shared.
class Tree {
  constructor(x, y, type) { this.x = x; this.y = y; this.type = type; }
}

const forest = [];
for (let i = 0; i < 1000; i++) {
  const type = TreeTypeFactory.get("Oak", "green"); // all share ONE TreeType
  forest.push(new Tree(Math.random(), Math.random(), type));
}
console.log(TreeTypeFactory.get("Oak", "green") === forest[0].type); // true — shared
```

## A4. `Symbol.species` (belongs with Tier 8)

**`Symbol.species`** lets a class control **which constructor** is used by methods that
return new instances (like `map`, `filter`, `slice`). Override it to make derived
methods return the base type instead of your subclass.

```js
class MyArray extends Array {
  // Tell derived methods (map/filter/slice) to produce plain Arrays, not MyArray.
  static get [Symbol.species]() { return Array; }
}

const arr = new MyArray(1, 2, 3);
const mapped = arr.map((x) => x * 2);

console.log(mapped instanceof MyArray); // false — thanks to Symbol.species
console.log(mapped instanceof Array);   // true
// Without the override, mapped would be a MyArray.
```

## A5. Entity vs Value Object — direct comparison (belongs with Tier 11)

Both are DDD building blocks, but they differ in **identity** and **mutability**.

```js
// ENTITY: equality by identity (id). Attributes may change over time.
class Customer {
  constructor(id, name) { this.id = id; this.name = name; }
  equals(other) { return other instanceof Customer && this.id === other.id; }
}

// VALUE OBJECT: equality by value. Immutable; no identity.
class Address {
  constructor(street, city) {
    this.street = street;
    this.city = city;
    Object.freeze(this); // immutable
  }
  equals(other) {
    return other instanceof Address &&
      this.street === other.street && this.city === other.city;
  }
  withCity(city) { return new Address(this.street, city); } // "change" = new object
}

const c1 = new Customer(1, "Asha");
const c2 = new Customer(1, "Asha Rao"); // renamed, SAME identity
console.log(c1.equals(c2)); // true — same id, still the same customer

const a1 = new Address("1 Main St", "Mumbai");
const a2 = new Address("1 Main St", "Mumbai");
console.log(a1.equals(a2)); // true — same values
console.log(a1 === a2);     // false — different instances
```

| | Entity | Value Object |
|--|--------|--------------|
| Identity | Has a unique id | None |
| Equality | By id | By value |
| Mutability | Usually mutable | Immutable |
| Example | Customer, Order | Money, Address, Color |

## A6. Object Lifecycle (belongs with Tier 11)

The **lifecycle** of an object is the span from creation to garbage collection. JS has
no destructors, but there are clear phases and a couple of lifecycle hooks.

**Phases:**
1. **Creation** — via `new`, a literal, factory, or `Object.create`. The constructor
   runs and initializes state.
2. **Use** — the object is referenced and its methods are called; its state evolves.
3. **Unreachability** — all references are dropped.
4. **Garbage collection** — the engine reclaims memory automatically (you don't
   control *when*).

```js
let user = { name: "Asha" }; // 1. created
user.name = "Ravi";           // 2. used / state changes
user = null;                  // 3. now unreachable -> eligible for GC
// 4. GC reclaims it later, automatically — no manual free().
```

**Cleanup hooks (advanced, use sparingly):**

```js
// FinalizationRegistry: run a callback AFTER an object is garbage-collected.
// Use only for optional cleanup (e.g., closing a cache entry) — never for critical logic,
// since timing is not guaranteed.
const registry = new FinalizationRegistry((heldValue) => {
  console.log(`cleaned up: ${heldValue}`);
});

let resource = { id: 1 };
registry.register(resource, "resource #1");
resource = null; // eventually triggers the cleanup callback (timing not guaranteed)
```

> **Guidance:** Don't rely on `FinalizationRegistry` for correctness. For deterministic
> cleanup (files, sockets), use an explicit `close()`/`dispose()` method and call it
> yourself (the Disposable pattern), e.g. in a `try/finally`.

### Appendix exercises

1. Use a `WeakSet` to ensure a one-time initialization runs at most once per object.
2. Implement a `Bridge`: one `Shape` abstraction with two renderers; swap at runtime.
3. Build a `Flyweight` factory for colored icons and prove two same-config icons share
   one shared object.
4. Subclass `Array` and use `Symbol.species` so `.filter()` returns a plain `Array`.
5. Model one `Entity` and one `Value Object`; demonstrate id-equality vs value-equality.
6. Add a `dispose()` method to a class and call it in a `try/finally` block.

---
---

# APPENDIX 2 — ADVANCED & ARCHITECTURAL GAP-FILLERS

Full coverage for the remaining items: object internals, advanced ES features,
event-driven architecture, more DDD, the architectural pattern family, concurrency &
state, and functional-OOP hybrid concepts.

## B1. Object Internals — Internal Slots & Internal Methods

The ECMAScript spec defines objects in terms of hidden **internal slots** (state) and
**internal methods** (operations), written in double brackets `[[...]]`. You can't
access them directly from code — the engine uses them — but understanding them explains
*why* JS behaves as it does.

- **Internal slots** = hidden fields on an object, e.g. `[[Prototype]]` (its prototype
  link), `[[Extensible]]` (can new props be added), `[[PrivateFieldValues]]`.
- **Internal methods** = the operations every object must support:
  - **`[[Get]]`** — runs on a property read (`obj.x`).
  - **`[[Set]]`** — runs on a property write (`obj.x = 1`).
  - **`[[GetPrototypeOf]]` / `[[SetPrototypeOf]]`** — read/write the prototype.
  - **`[[Call]]`** — invoke a function (`fn()`).
  - **`[[Construct]]`** — construct with `new`.
  - **`[[Delete]]`, `[[HasProperty]]`, `[[DefineOwnProperty]]`, `[[OwnPropertyKeys]]`**.

A **`Proxy`** (Tier 8) is special because its *traps correspond directly to these
internal methods* — a `get` trap intercepts `[[Get]]`, a `set` trap intercepts `[[Set]]`,
`construct` intercepts `[[Construct]]`, and so on.

```js
// This Proxy makes the [[Get]] and [[Set]] internal methods observable:
const observed = new Proxy({}, {
  get(t, k) { console.log(`[[Get]] ${String(k)}`); return Reflect.get(t, k); },
  set(t, k, v) { console.log(`[[Set]] ${String(k)}=${v}`); return Reflect.set(t, k, v); },
});
observed.x = 5; // logs: [[Set]] x=5
observed.x;     // logs: [[Get]] x
```

## B2. Memory: Reachability & Weak References

### Reachability (how GC decides what to keep)

JavaScript's garbage collector keeps any value that is **reachable** from a "root"
(global object, current call stack, etc.). When nothing can reach a value, it becomes
eligible for collection.

```js
let a = { data: 1 };   // reachable via `a`
let b = a;             // still reachable via `a` and `b`
a = null;              // reachable via `b`
b = null;              // now UNREACHABLE -> eligible for garbage collection
```

### Strong vs Weak References

- A normal reference is **strong** — it keeps the object alive.
- **`WeakRef`** holds an object **weakly** — it does not prevent collection. Call
  `.deref()` to get the object (or `undefined` if it's already gone).

```js
let big = { payload: "..." };
const weak = new WeakRef(big);

console.log(weak.deref()?.payload); // "..." (still alive)
big = null; // remove the only strong reference
// Later, after GC, weak.deref() may return undefined.
```

Pair with **`FinalizationRegistry`** (Appendix A6) for post-collection cleanup. Use
`WeakRef`/`WeakMap`/`WeakSet` for caches and metadata that must not cause memory leaks.

## B3. Advanced ES Features

### Decorators (`@decorator`) — Stage 3 / TypeScript

A **decorator** is a function that wraps/annotates a class or its members using `@`
syntax. Standardized decorators are new (Stage 3); they're widely used today via
TypeScript and frameworks (Angular, NestJS).

```js
// A method decorator that logs calls (modern decorators signature).
function log(originalMethod, context) {
  return function (...args) {
    console.log(`calling ${String(context.name)}`);
    return originalMethod.call(this, ...args);
  };
}

class Service {
  @log
  fetch(id) { return `item ${id}`; }
}
// new Service().fetch(1) -> logs "calling fetch", returns "item 1"
```

> Requires a toolchain that supports decorators (TypeScript, or Babel/SWC with the
> decorators plugin). Plain Node/browsers may not run `@` syntax natively yet.

### Metadata Reflection

**Metadata** attaches extra descriptive data to classes/members, read later via
reflection — the backbone of dependency-injection frameworks. In the ecosystem this is
the `reflect-metadata` library with `Reflect.defineMetadata` / `Reflect.getMetadata`.

```js
// Conceptual (with the reflect-metadata polyfill):
// Reflect.defineMetadata("role", "admin", MyClass);
// Reflect.getMetadata("role", MyClass); // "admin"

// Plain-JS stand-in using a WeakMap as a metadata store:
const metadata = new WeakMap();
function setMeta(target, data) { metadata.set(target, data); }
function getMeta(target) { return metadata.get(target); }

class Controller {}
setMeta(Controller, { route: "/users" });
console.log(getMeta(Controller)); // { route: "/users" }
```

### Dynamic Imports — modules loaded on demand

`import()` is a function form of import that returns a **Promise**, letting you load a
module at runtime (code-splitting, lazy loading).

```js
async function loadTool() {
  const module = await import("./heavyTool.js"); // loaded only when needed
  module.run();
}
// Static import loads up front; dynamic import() defers until called.
```

### Modules as Objects

An ES module's namespace behaves like a (read-only) object: its exports are properties.
`import * as X` gives you that namespace object.

```js
// import * as math from "./math.js";
// math.add(1, 2);          // exports accessed like object properties
// Object.keys(math);        // lists exported names
// Module bindings are live and read-only — you can't reassign math.add.
```

## B4. Event-Driven Architecture, Message Passing & Event Sourcing

### Message Passing

Objects coordinate by **sending messages** (calling methods / dispatching events)
rather than touching each other's internals — the essence of OOP per Alan Kay.

```js
class Actor {
  receive(message) { return `handled: ${message.type}`; }
}
const actor = new Actor();
actor.receive({ type: "START" }); // communication via messages, not shared state
```

### Event-Driven Architecture (EDA)

Components emit and react to **events** instead of calling each other directly,
yielding loose coupling. Built on Pub/Sub and Event Emitters (Tier 11).

```js
class EventBus {
  #handlers = new Map();
  on(type, fn) {
    if (!this.#handlers.has(type)) this.#handlers.set(type, []);
    this.#handlers.get(type).push(fn);
  }
  emit(type, payload) {
    (this.#handlers.get(type) ?? []).forEach((fn) => fn(payload));
  }
}
```

### Event Sourcing

Instead of storing current state, store the **sequence of events** that produced it.
Rebuild state by replaying events. Powerful for audit logs and undo.

```js
class Account {
  #events = [];
  apply(event) { this.#events.push(event); }           // record, don't overwrite
  get balance() {                                        // derive state from events
    return this.#events.reduce((bal, e) =>
      e.type === "deposit" ? bal + e.amount :
      e.type === "withdraw" ? bal - e.amount : bal, 0);
  }
}

const acc = new Account();
acc.apply({ type: "deposit", amount: 100 });
acc.apply({ type: "withdraw", amount: 30 });
console.log(acc.balance); // 70 — computed by replaying events
```

## B5. More DDD — Bounded Context & Domain Event

### Bounded Context

A **bounded context** is an explicit boundary within which a domain model and its terms
have one consistent meaning. "Customer" in Sales may differ from "Customer" in Support;
each lives in its own context, communicating via well-defined contracts.

```js
// Sales context
const SalesContext = {
  Customer: class { constructor(id, creditLimit) { this.id = id; this.creditLimit = creditLimit; } },
};
// Support context — same word, different model
const SupportContext = {
  Customer: class { constructor(id, openTickets) { this.id = id; this.openTickets = openTickets; } },
};
// They stay separate; integration happens through explicit mapping, not shared classes.
```

### Domain Event

A **domain event** records something meaningful that happened in the domain (past
tense: `OrderPlaced`, `PaymentReceived`). Other parts react to it.

```js
class OrderPlaced {
  constructor(orderId) {
    this.type = "OrderPlaced";
    this.orderId = orderId;
    this.occurredAt = new Date();
  }
}
// Raised by the domain, then published on an event bus for handlers to consume.
```

## B6. Architectural Patterns

High-level ways to organize an entire application. Sketches, not full apps.

### MVC — Model / View / Controller

```js
class Model { constructor() { this.data = 0; } set(v) { this.data = v; } }
class View { render(data) { return `<p>${data}</p>`; } }
class Controller {
  constructor(model, view) { this.model = model; this.view = view; }
  update(v) { this.model.set(v); return this.view.render(this.model.data); }
}
```

- **MVC** — Controller handles input, updates Model, selects View.
- **MVP** — a **Presenter** fully mediates; the View is passive and calls into the
  Presenter (common in older desktop/Android UIs).
- **MVVM** — a **ViewModel** exposes bindable state; the View binds to it declaratively
  (Angular, Vue, WPF). Two-way data binding replaces manual view updates.

```js
// MVVM sketch — ViewModel holds bindable state
class CounterViewModel {
  #count = 0;
  get count() { return this.#count; }
  increment() { this.#count++; } // the View binds to `count` and re-renders
}
```

### Hexagonal / Ports & Adapters

Also called **Ports and Adapters**. The core domain defines **ports** (interfaces);
**adapters** connect external tech (DB, HTTP, UI) to those ports. The domain never
depends on infrastructure — infrastructure depends on the domain.

```js
// Port: what the domain needs (an abstraction)
class UserRepositoryPort {
  save(user) { throw new Error("implement"); }
}
// Adapter: a concrete implementation plugged into the port
class InMemoryUserAdapter extends UserRepositoryPort {
  #store = new Map();
  save(user) { this.#store.set(user.id, user); }
}
// Core service depends on the PORT, not the adapter (DIP from Tier 9).
class UserCore {
  constructor(repoPort) { this.repo = repoPort; }
  register(user) { this.repo.save(user); }
}
new UserCore(new InMemoryUserAdapter()).register({ id: 1 });
```

### Clean Architecture / Onion Architecture

Both arrange code in concentric layers with the **dependency rule**: dependencies point
**inward**, toward the domain. Entities at the center, then use cases, then interface
adapters, then frameworks/drivers on the outside. Onion is the same idea (domain core
wrapped by application, then infrastructure). Inner layers know nothing about outer ones.

```
[ Frameworks/UI/DB ]  ->  [ Interface Adapters ]  ->  [ Use Cases ]  ->  [ Entities ]
         outer  ----------------- depends inward ----------------->  inner (knows nothing outward)
```

## B7. Concurrency & State

### Mutable vs Immutable State (named)

- **Mutable state** — changed in place; simple but risky when shared.
- **Immutable state** — never changed; updates produce new objects (Tier 7). Core to
  React/Redux and easier to reason about concurrently.

```js
// Mutable
const cart = { items: [] };
cart.items.push("book"); // changed in place

// Immutable update
const state = { count: 0 };
const next = { ...state, count: state.count + 1 }; // new object, original intact
```

### State Machines

A **finite state machine** has a fixed set of states and allowed transitions. Makes
illegal states impossible and logic explicit.

```js
class TrafficLight {
  #state = "red";
  static #transitions = { red: "green", green: "yellow", yellow: "red" };
  next() {
    this.#state = TrafficLight.#transitions[this.#state];
    return this.#state;
  }
  get state() { return this.#state; }
}
const light = new TrafficLight();
console.log(light.next(), light.next(), light.next()); // green yellow red
```

### Actor Model

Concurrency via independent **actors** that own private state and communicate only by
**asynchronous messages** — no shared memory, so no locks. In JS this maps to Web
Workers / Node worker threads exchanging messages.

```js
// Conceptual actor: private state, mailbox-style message handling.
class CounterActor {
  #count = 0;
  send(message) { // process one message at a time
    if (message === "inc") this.#count++;
    if (message === "get") return this.#count;
  }
}
// Real actors run in separate workers and pass messages via postMessage().
```

## B8. Functional-OOP Hybrid Concepts

JavaScript blends OOP and functional styles. These functional tools pair naturally with
objects.

### First-Class & Higher-Order Functions, Closures (recap)

Functions are values; functions that take/return functions are **higher-order**;
closures capture surrounding variables (covered in Tier 2 and Tier 11).

### Currying

Transform a multi-arg function into a chain of single-arg functions.

```js
const curriedAdd = (a) => (b) => (c) => a + b + c;
console.log(curriedAdd(1)(2)(3)); // 6
```

### Partial Application

Fix some arguments now, supply the rest later (via `bind` or a closure).

```js
function multiply(a, b) { return a * b; }
const double = multiply.bind(null, 2); // fix a = 2
console.log(double(5)); // 10

// Closure-based partial:
const partial = (fn, ...fixed) => (...rest) => fn(...fixed, ...rest);
const addTax = partial((rate, price) => price * (1 + rate), 0.18);
console.log(addTax(100)); // 118
```

### Function Composition

Combine small functions into a pipeline, feeding each output into the next.

```js
const compose = (...fns) => (x) => fns.reduceRight((acc, fn) => fn(acc), x);
const pipe = (...fns) => (x) => fns.reduce((acc, fn) => fn(acc), x);

const inc = (n) => n + 1;
const double = (n) => n * 2;

console.log(compose(double, inc)(5)); // double(inc(5)) = 12
console.log(pipe(double, inc)(5));    // inc(double(5)) = 11
```

### Appendix 2 exercises

1. Build a logging `Proxy` and explain which internal method (`[[Get]]`/`[[Set]]`) each
   trap corresponds to.
2. Use `WeakRef` + `FinalizationRegistry` to build a cache that lets entries be collected.
3. Implement an event-sourced `ShoppingCart` whose state is derived by replaying events.
4. Model a feature two ways: MVC and MVVM; note what moves between Controller and ViewModel.
5. Implement Ports & Adapters: a domain service depending on a repository port, with two
   adapters (in-memory and a fake "API").
6. Write a `curry` helper and use it to build a partially-applied function.
7. Build `pipe`/`compose` and chain three transformations.
8. Implement a state machine for a document (`draft → review → published`) that rejects
   illegal transitions.
