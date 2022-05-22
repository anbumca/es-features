JavaScript Operators
====================

In this tutorial, you will learn about different operators available in JavaScript and how to use them with the help of examples.

What is an Operator?
--------------------

In JavaScript, an operator is a special symbol used to perform operations on operands (values and variables). For example,

    2 + 3; // 5

Here `+` is an operator that performs addition, and `2` and `3` are operands.

* * *

JavaScript Operator Types
-------------------------

Here is a list of different operators you will learn in this tutorial.

*   Assignment Operators
*   Arithmetic Operators
*   Comparison Operators
*   Logical Operators
*   Bitwise Operators
*   String Operators
*   Other Operators

* * *

JavaScript Assignment Operators
-------------------------------

Assignment operators are used to **assign** values to variables. For example,

    const x = 5;

Here, the `=` operator is used to assign value `5` to variable `x`.

Here's a list of commonly used assignment operators:

Operator

Name

Example

`=`

Assignment operator

`a = 7; // 7`

`+=`

Addition assignment

`a += 5; // a = a + 5`

`-=`

Subtraction Assignment

`a -= 2; // a = a - 2`

`*=`

Multiplication Assignment

`a *= 3; // a = a * 3`

`/=`

Division Assignment

`a /= 2; // a = a / 2`

`%=`

Remainder Assignment

`a %= 2; // a = a % 2`

`**=`

Exponentiation Assignment

`a **= 2; // a = a**2`

**Note:** The commonly used assignment operator is `=`. You will understand other assignment operators such as `+=`, `-=`, `*=` etc. once we learn arithmetic operators.

* * *

JavaScript Arithmetic Operators
-------------------------------

Arithmetic operators are used to perform **arithmetic calculations**. For example,

    const number = 3 + 5; // 8

Here, the `+` operator is used to add two operands.

Operator

Name

Example

`+`

Addition

`x + y`

`-`

Subtraction

`x - y`

`*`

Multiplication

`x * y`

`/`

Division

`x / y`

`%`

Remainder

`x % y`

`++`

Increment (increments by 1)

`++x` or `x++`

`--`

Decrement (decrements by 1)

`--x` or `x--`

`**`

Exponentiation (Power)

`x ** y`

* * *

### Example 1: Arithmetic operators in JavaScript

    let x = 5;
    let y = 3;

    // addition
    console.log('x + y = ', x + y);  // 8

    // subtraction
    console.log('x - y = ', x - y);  // 2

    // multiplication
    console.log('x * y = ', x * y);  // 15

    // division
    console.log('x / y = ', x / y);  // 1.6666666666666667

    // remainder
    console.log('x % y = ', x % y);   // 2

    // increment
    console.log('++x = ', ++x); // x is now 6
    console.log('x++ = ', x++); // prints 6 and then increased to 7
    console.log('x = ', x);     // 7

    // decrement
    console.log('--x = ', --x); // x is now 6
    console.log('x-- = ', x--); // prints 6 and then decreased to 5
    console.log('x = ', x);     // 5

    //exponentiation
    console.log('x ** y =', x ** y);

[Run Code](/javascript/online-compiler)

Visit [++ and -- operator](/article/increment-decrement-operator-difference-prefix-postfix) to learn more.

**Note**: The `**` operator was introduced in ECMAScript 2016 and some browsers may not support them. To learn more, visit [JavaScript exponentiation browser support](https://caniuse.com/#search=Exponentiation%20operator).

* * *

JavaScript Comparison Operators
-------------------------------

Comparison operators **compare** two values and return a boolean value, either `true` or `false`. For example,

    const a = 3, b = 2;
    console.log(a > b); // true

[Run Code](/javascript/online-compiler)

Here, the comparison operator `>` is used to compare whether a is greater than b.

Operator

Description

Example

`==`

**Equal to**: returns `true` if the operands are equal

`x == y`

`!=`

**Not equal to**: returns `true` if the operands are not equal

`x != y`

`===`

**Strict equal to**: `true` if the operands are equal and of the same type

`x === y`

`!==`

**Strict not equal to**: `true` if the operands are equal but of different type or not equal at all

`x !== y`

`>`

**Greater than**: `true` if left operand is greater than the right operand

`x > y`

`>=`

**Greater than or equal to**: `true` if left operand is greater than or equal to the right operand

`x >= y`

`<`

**Less than**: `true` if the left operand is less than the right operand

`x < y`

`<=`

**Less than or equal to**: `true` if the left operand is less than or equal to the right operand

`x <= y`

* * *

### Example 2: Comparison operators in JavaScript

    // equal operator
    console.log(2 == 2); // true
    console.log(2 == '2'); // true

    // not equal operator
    console.log(3 != 2); // true
    console.log('hello' != 'Hello'); // true

    // strict equal operator
    console.log(2 === 2); // true
    console.log(2 === '2'); // false

    // strict not equal operator
    console.log(2 !== '2'); // true
    console.log(2 !== 2); // false

[Run Code](/javascript/online-compiler)

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Comparison operators are used in decision-making and loops. You will learn about the use of comparison operators in detail in later tutorials.

* * *

### JavaScript Logical Operators

Logical operators perform logical operations and return a boolean value, either `true` or `false`. For example,

    const x = 5, y = 3;
    (x < 6) && (y < 5); // true

Here, `&&` is the logical operator **AND**. Since both `x < 6` and `y < 5` are `true`, the result is `true`.

Operator

Description

Example

`&&`

**Logical AND**: `true` if both the operands are `true`, else returns `false`

`x && y`

`||`

**Logical OR**: `true` if either of the operands is `true`; returns false if both are `false`

`x || y`

`!`

**Logical NOT**: `true` if the operand is `false` and vice-versa.

`!x`

* * *

### Example 3: Logical Operators in JavaScript

    // logical AND
    console.log(true && true); // true
    console.log(true && false); // false

    // logical OR
    console.log(true || false); // true

    // logical NOT
    console.log(!true); // false

[Run Code](/javascript/online-compiler)

**Output**

true
false
true
false

Logical operators are used in decision making and loops. You will learn about the use of logical operators in detail in later tutorials.

* * *

### JavaScript Bitwise Operators

Bitwise operators perform operations on binary representations of numbers.

Operator

Description

`&`

Bitwise AND

`|`

Bitwise OR

`^`

Bitwise XOR

`~`

Bitwise NOT

`<<`

Left shift

`>>`

Sign-propagating right shift

`>>>`

Zero-fill right shift

Bitwise operators are rarely used in everyday programming. If you are interested, visit [JavaScript Bitwise Operators](https://www.programiz.com/javascript/bitwise-operators) to learn more.

* * *

### JavaScript String Operators

In JavaScript, you can also use the `+` operator to concatenate (join) two or more strings.

### Example 4: String operators in JavaScript

    // concatenation operator
    console.log('hello' + 'world');

    let a = 'JavaScript';

    a += ' tutorial';  // a = a + ' tutorial';
    console.log(a);

[Run Code](/javascript/online-compiler)

**Output**

helloworld
JavaScript tutorial

**Note:** When `+` is used with strings, it performs concatenation. However, when `+` is used with numbers, it performs addition.

* * *

### Other JavaScript Operators

Here's a list of other operators available in JavaScript. You will learn about these operators in later tutorials.

Operator

Description

Example

`,`

evaluates multiple operands and returns the value of the last operand.

`let a = (1, 3 , 4); // 4`

`?:`

returns value based on the condition

`(5 > 3) ? 'success' : 'error'; // "success"`

`delete`

deletes an object's property, or an element of an array

`delete x`

`typeof`

returns a string indicating the data type

`typeof 3; // "number"`

`void`

discards the expression's return value

`void(x)`

`in`

returns `true` if the specified property is in the object

`prop in object`

`instanceof`

returns `true` if the specified object is of of the specified object type

`object instanceof object_type`


===================================

JavaScript Data Types
=====================

In this tutorial, you will learn about the various data types available in JavaScript with the help of examples.

There are different types of data that we can use in a JavaScript program. For example,

    const x = 5;
    const y = "Hello";

Here,

*   5 is an integer data.
*   "Hello" is a string data.

* * *

JavaScript Data Types
---------------------

There are eight basic data types in JavaScript. They are:

Data Types

Description

Example

`String`

represents textual data

`'hello'`, `"hello world!"` etc

`Number`

an integer or a floating-point number

`3`, `3.234`, `3e-2` etc.

`BigInt`

an integer with arbitrary precision

`900719925124740999n` , `1n` etc.

`Boolean`

Any of two values: true or false

`true` and `false`

`undefined`

a data type whose variable is not initialized

`let a;`

`null`

denotes a `null` value

`let a = null;`

`Symbol`

data type whose instances are unique and immutable

`let value = Symbol('hello');`

`Object`

key-value pairs of collection of data

`let student = { };`

Here, all data types except `Object` are primitive data types, whereas `Object` is non-primitive.

**Note:** The `Object` data type (non-primitive type) can store collections of data, whereas primitive data type can only store a single data.

* * *

JavaScript String
-----------------

`String` is used to store text. In JavaScript, strings are surrounded by quotes:

*   Single quotes: `'Hello'`
*   Double quotes: `"Hello"`
*   Backticks: `` `Hello` ``

For example,

    //strings example
    const name = 'ram';
    const name1 = "hari";
    const result = `The names are ${name} and ${name1}`;

Single quotes and double quotes are practically the same and you can use either of them.

Backticks are generally used when you need to include variables or expressions into a string. This is done by wrapping variables or expressions with `${variable or expression}` as shown above.

You will learn about the use of backticks in the [JavaScript String](https://www.programiz.com/javascript/string) tutorial.

* * *

JavaScript Number
-----------------

`Number` represents integer and floating numbers (decimals and exponentials). For example,

    const number1 = 3;
    const number2 = 3.433;
    const number3 = 3e5 // 3 * 10^5

A number type can also be `+Infinity`, `-Infinity`, and `NaN` (not a number). For example,

    const number1 = 3/0;
    console.log(number1); // Infinity

    const number2 = -3/0;
    console.log(number2); // -Infinity

    // strings can't be divided by numbers
    const number3 = "abc"/3;
    console.log(number3);  // NaN

[Run Code](/javascript/online-compiler)

* * *

JavaScript BigInt
-----------------

In JavaScript, `Number` type can only represent numbers less than **(253** **\- 1)** and more than **\-(253** **\- 1)**. However, if you need to use a larger number than that, you can use the `BigInt` data type.

A `BigInt` number is created by appending **n** to the end of an integer. For example,

    // BigInt value
    const value1 = 900719925124740998n;

    // Adding two big integers
    const result1 = value1 + 1n;
    console.log(result1); // "900719925124740999n"

    const value2 = 900719925124740998n;

    // Error! BitInt and number cannot be added
    const result2 = value2 + 1;
    console.log(result2);

[Run Code](/javascript/online-compiler)

**Output**

900719925124740999n
Uncaught TypeError: Cannot mix BigInt and other types

**Note:** `BigInt` was introduced in the newer version of JavaScript and is not supported by many browsers including Safari. Visit [JavaScript BigInt support](https://caniuse.com/#feat=bigint) to learn more.

* * *

JavaScript Boolean
------------------

This data type represents logical entities. `Boolean` represents one of two values: `true` or `false`. It is easier to think of it as a yes/no switch. For example,

    const dataChecked = true;
    const valueCounted = false;

You will learn more about booleans in the [JavaScript Comparison and Logical Operators](/javascript/comparison-logical) tutorial.

* * *

JavaScript undefined
--------------------

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

The `undefined` data type represents **value that is not assigned**. If a variable is declared but the value is not assigned, then the value of that variable will be `undefined`. For example,

    let name;
    console.log(name); // undefined

[Run Code](/javascript/online-compiler)

It is also possible to explicitly assign a variable value `undefined`. For example,

    let name = undefined;
    console.log(name); // undefined

[Run Code](/javascript/online-compiler)

**Note:** It is recommended not to explicitly assign `undefined` to a variable. Usually, `null` is used to assign 'unknown' or 'empty' value to a variable.

* * *

JavaScript null
---------------

In JavaScript, `null` is a special value that represents **empty** or **unknown value**. For example,

    const number = null;

The code above suggests that the number variable is empty.

**Note**: `null` is not the same as NULL or Null.

* * *

JavaScript Symbol
-----------------

This data type was introduced in a newer version of JavaScript (from ES2015).

A value having the data type `Symbol` can be referred to as a **symbol value**. `Symbol` is an immutable primitive value that is unique. For example,

    // two symbols with the same description

    const value1 = Symbol('hello');
    const value2 = Symbol('hello');

Though value1 and value2 both contain `'hello'`, they are different as they are of the `Symbol` type.

Visit [JavaScript Symbol](https://www.programiz.com/javascript/symbol) to learn more.

* * *

JavaScript Object
-----------------

An `object` is a complex data type that allows us to store collections of data. For example,

    const student = {
        firstName: 'ram',
        lastName: null,
        class: 10
    };

You will learn about [JavaScript Objects](https://www.programiz.com/javascript/object) in later tutorials.

* * *

JavaScript Type
---------------

JavaScript is a dynamically typed (loosely typed) language. JavaScript automatically determines the variables' data type for you.

It also means that a variable can be of one data type and later it can be changed to another data type. For example,

    // data is of undefined type
    let data;

    // data is of integer type
    data = 5;

    // data is of string type
    data = "JavaScript Programming";

* * *

JavaScript typeof
-----------------

To find the type of a variable, you can use the `typeof` operator. For example,

    const name = 'ram';
    typeof(name); // returns "string"

    const number = 4;
    typeof(number); //returns "number"

    const valueChecked = true;
    typeof(valueChecked); //returns "boolean"

    const a = null;
    typeof(a); // returns "object"

Notice that `typeof` returned `"object"` for the `null` type. This is a known issue in JavaScript since its first release.

JavaScript Variables and Constants
==================================

In this tutorial, you will learn about JavaScript variables and constants, and also how to initialize and use them with the help of examples.

JavaScript Variables
--------------------

In programming, a variable is a container (storage area) to hold data. For example,

    let num = 5;

Here, `num` is a variable. It's storing **5**.

* * *

### JavaScript Declare Variables

In JavaScript, we use either `var` or `let` keyword to declare variables. For example,

    var x;
    let y;

Here, x and y are variables.

* * *

### JavaScript var Vs let

Both `var` and `let` are used to declare variables. However, there are some differences between them.

var

let

`var` is used in the older versions of JavaScript

`let` is the new way of declaring variables starting **ES6 (ES2015)**.

`var` is function scoped (will be discussed in later tutorials).

`let` is block scoped (will be discussed in later tutorials).

For example, `var x;`

For example, `let y;`

**Note:** It is recommended we use `let` instead of `var`. However, there are a few browsers that do not support `let`. Visit [JavaScript let browser support](https://caniuse.com/#feat=let) to learn more.

* * *

### JavaScript Initialize Variables

We use the assignment operator `=` to assign a value to a variable.

    let x;
    x = 5;

Here, **5** is assigned to variable x.

You can also initialize variables during its declaration.

    let x = 5;
    let y = 6;

In JavaScript, it's possible to declare variables in a single statement.

    let x = 5, y = 6, z = 7;

* * *

If you use a variable without initializing it, it will have an `undefined` value.

    let x; // x is the name of the variable

    console.log(x); // undefined

Here x is the variable name and since it does not contain any value, it will be undefined.

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

You will learn about `undefined` and other data types in the next tutorial in detail.

* * *

### Change the Value of Variables

It's possible to change the value stored in the variable. For example,

    // 5 is assigned to variable x
    let x = 5;
    console.log(x); // 5

    // vaue of variable x is changed
    x = 3;
    console.log(x); // 3

[Run Code](/javascript/online-compiler)

The value of a variable may **vary**. Hence, the name **variable**.

* * *

### Rules for Naming JavaScript Variables

The rules for naming variables are:

1.  Variable names must start with either a letter, an underscore `_`, or the dollar sign `$`. For example,

        //valid
        let a = 'hello';
        let _a = 'hello';
        let $a = 'hello';

2.  Variable names cannot start with numbers. For example,

        //invalid
        Let 1a = 'hello'; // this gives an error

3.  JavaScript is case-sensitive. So y and Y are different variables. For example,

        let y = "hi";
        let Y = 5;

        console.log(y); // hi
        console.log(Y); // 5

    [Run Code](/javascript/online-compiler)

4.  [Keywords](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords) cannot be used as variable names. For example,

        //invalid
        let new = 5; // Error! new is a keyword.


**Notes:**

*   Though you can name variables in any way you want, it's a good practice to give a descriptive variable name. If you are using a variable to store the number of apples, it better to use apples or numberOfApples rather than x or n.
*   In JavaScript, the variable names are generally written in camelCase if it has multiple words. For example, firstName, annualSalary, etc.

* * *

JavaScript Constants
--------------------

The `const` keyword was also introduced in the **ES6(ES2015)** version to create constants. For example,

    const x = 5;

Once a constant is initialized, we cannot change its value.

    const x = 5;
    x = 10;  // Error! constant cannot be changed.
    console.log(x)

[Run Code](/javascript/online-compiler)

Simply, a constant is a type of variable whose value cannot be changed.

Also, you cannot declare a constant without initializing it. For example,

    const x;  // Error! Missing initializer in const declaration.
    x = 5;
    console.log(x)

[Run Code](/javascript/online-compiler)

**Note:** If you are sure that the value of a variable won't change throughout the program, it's recommended to use `const`. However, there are a few browsers that do not support `const`. Visit [JavaScript const browser support](https://caniuse.com/#feat=const) to learn more.

* * *

Now that you know about variables, you will learn about different types of data a variable can store in the next tutorial.

JavaScript Comparison and Logical Operators
===========================================

In this tutorial, you will learn about the Comparison operators and Logical operators with the help of examples.

JavaScript Comparison Operators
-------------------------------

Comparison operators compare two values and give back a boolean value: either `true` or `false`. Comparison operators are used in [decision making](/javascript/if-else) and [loops](/javascript/for-loop).

Operator

Description

Example

`==`

**Equal to**: `true` if the operands are equal

`5==5; //true`

`!=`

**Not equal to**: `true` if the operands are not equal

`5!=5; //false`

`===`

**Strict equal to**: `true` if the operands are equal and of the same type

`5==='5'; //false`

`!==`

**Strict not equal to**: `true` if the operands are equal but of different type or not equal at all

`5!=='5'; //true`

`>`

**Greater than**: `true` if the left operand is greater than the right operand

`3>2; //true`

`>=`

**Greater than or equal to**: `true` if the left operand is greater than or equal to the right operand

`3>=3; //true`

`<`

**Less than**: `true` if the left operand is less than the right operand

`3<2; //false`

`<=`

**Less than or equal to**: `true` if the left operand is less than or equal to the right operand

`2<=2; //true`

* * *

### Example 1: Equal to Operator

    const a = 5, b = 2, c = 'hello';

    // equal to operator
    console.log(a == 5);     // true
    console.log(b == '2');   // true
    console.log(c == 'Hello');  // false

[Run Code](/javascript/online-compiler)

`==` evaluates to `true` if the operands are equal.

**Note**: In JavaScript, `==` is a comparison operator, whereas `=` is an assignment operator. If you mistakenly use `=` instead of `==`, you might get unwanted result.

* * *

### Example 2: Not Equal to Operator

    const a = 3, b = 'hello';

    // not equal operator
    console.log(a != 2); // true
    console.log(b != 'Hello'); // true

[Run Code](/javascript/online-compiler)

`!=` evaluates to `true` if the operands are not equal.

* * *

### Example 3: Strict Equal to Operator

    const a = 2;

    // strict equal operator
    console.log(a === 2); // true
    console.log(a === '2'); // false

[Run Code](/javascript/online-compiler)

`===` evaluates to`true` if the operands are equal and of the same type. Here **2** and **'2'** are the same numbers but the data type is different. And `===` also checks for the data type while comparing.

* * *

**Note**: The difference between `==` and `===` is that:

`==` evaluates to `true` if the operands are equal, however, `===` evaluates to `true` only if the operands are equal and of the same type

* * *

### Example 4: Strict Not Equal to Operator

     const a = 2, b = 'hello';

    // strict not equal operator
    console.log(a !== 2); // false
    console.log(a !== '2'); // true
    console.log(b !== 'Hello'); // true

[Run Code](/javascript/online-compiler)

`!==` evaluates to `true` if the operands are strictly not equal. It's the complete opposite of strictly equal `===`.

In the above example, `2 != '2'` gives `true`. It's because their types are different even though they have the same value.

* * *

### Example 5: Greater than Operator

    const a = 3;

    // greater than operator
    console.log(a > 2); // true

[Run Code](/javascript/online-compiler)

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

`>` evaluates to `true` if the left operand is greater than the right operand.

* * *

### Example 6: Greater than or Equal to Operator

    const a = 3;

    // greater than or equal operator
    console.log(a >= 3); //true

[Run Code](/javascript/online-compiler)

`>=` evaluates to `true` if the left operand is greater than or equal to the right operand.

* * *

### Example 7: Less than Operator

    const a = 3, b = 2;

    // less than operator
    console.log(a < 2); // false
    console.log(b < 3); // true

[Run Code](/javascript/online-compiler)

`<` evaluates to `true` if the left operand is less than the right operand.

* * *

### Example 8: Less than or Equal to Operator

    const a = 2;

    // less than or equal operator
    console.log(a <= 3) // true
    console.log(a <= 2); // true

[Run Code](/javascript/online-compiler)

`<=` evaluates to `true` if the left operand is less than or equal to the right operand.

* * *

JavaScript Logical Operators
----------------------------

Logical operators perform logical operations: **AND**, **OR** and **NOT**.

Operator

Description

Example

`&&`

**Logical AND**: `true` if both the operands/boolean values are true, else evaluates to `false`

`true && false; // false`

`||`

**Logical OR**: `true` if either of the operands/boolean values is `true`. evaluates to `false` if both are `false`

`true || false; // true`

`!`

**Logical NOT**: `true` if the operand is `false` and vice-versa.

`!true; // false`

* * *

### Example 9: Logical AND Operator

    const a = true, b = false;
    const c = 4;

    // logical AND
    console.log(a && a); // true
    console.log(a && b);  // false

    console.log((c > 2) && (c < 2)); // false

[Run Code](/javascript/online-compiler)

`&&` evaluates to `true` if both the operands are `true`, else evaluates to `false`.

**Note:** You can also use logical operators with numbers. In JavaScript, 0 is `false` and all non-zero values are `true`.

* * *

### Example 10: Logical OR Operator

    const a = true, b = false, c = 4;


    // logical OR
    console.log(a || b); // true
    console.log(b || b); // false
    console.log((c>2) || (c<2)); // true

[Run Code](/javascript/online-compiler)

`||` evaluates to `true` if either of the operands is `true`. If both operands are `false`, the result is `false`.

* * *

### Example 11: Logical NOT Operator

    const a = true, b = false;

    // logical NOT
    console.log(!a); // false
    console.log(!b); // true

[Run Code](/javascript/online-compiler)

`!` evaluates to `true` if the operand is `false` and vice-versa.

JavaScript if...else Statement
==============================

In this tutorial, you will learn about the if...else statement to create decision making programs with the help of examples.

In computer programming, there may arise situations where you have to run a block of code among more than one alternatives. For example, assigning grades **A**, **B** or **C** based on marks obtained by a student.

In such situations, you can use the JavaScript `if...else` statement to create a program that can make decisions.

* * *

In JavaScript, there are three forms of the `if...else` statement.

1.  **if** statement
2.  **if...else** statement
3.  **if...else if...else** statement

* * *

JavaScript if Statement
-----------------------

The syntax of the `if` statement is:

    if (condition) {
        // the body of if
    }

The `if` statement evaluates the condition inside the parenthesis `()`.

1.  If the condition is evaluated to `true`, the code inside the body of `if` is executed.
2.  If the condition is evaluated to `false`, the code inside the body of `if` is skipped.

**Note:** The code inside `{ }` is the body of the `if` statement.

![Working of if statement in JavaScript](//cdn.programiz.com/sites/tutorial2program/files/js-if-statement_0.png "Working of if statement in JavaScript")

Working of the if Statement

* * *

### Example 1: if Statement

    // check if the number is positive

    const number = prompt("Enter a number: ");

    // check if number is greater than 0
    if (number > 0) {
     // the body of the if statement
      console.log("The number is positive");
    }

    console.log("The if statement is easy");

[Run Code](/javascript/online-compiler)

**Output 1**

Enter a number: 2
The number is positive
The if statement is easy

Suppose the user entered **2**. In this case, the condition `number > 0` evaluates to `true`. And, the body of the `if` statement is executed.

**Output 2**

Enter a number: -1
The if statement is easy

Suppose the user entered **\-1**. In this case, the condition `number > 0` evaluates to `false`. Hence, the body of the `if` statement is skipped.

Since `console.log("The if statement is easy");` is outside the body of the `if` statement, it is always executed.

Comparison and logical operators are used in conditions. So to learn more about comparison and logical operators, you can visit [JavaScript Comparison and Logical Operators](/javascript/comparison-logical).

* * *

JavaScript if...else statement
------------------------------

An `if` statement can have an optional `else` clause. The syntax of the `if...else` statement is:

    if (condition) {
        // block of code if condition is true
    } else {
       // block of code if condition is false
    }

The `if..else` statement evaluates the **condition** inside the parenthesis.

If the condition is evaluated to `true`,

1.  the code inside the body of `if` is executed
2.  the code inside the body of `else` is skipped from execution


If the condition is evaluated to `false`,

1.  the code inside the body of `else` is executed
2.  the code inside the body of `if` is skipped from execution

![Working of if-else statement in JavaScript](//cdn.programiz.com/sites/tutorial2program/files/js-if-else-statement.png "Working of if-else statement in JavaScript")

Working of the if...else statement

* * *

### Example 2: if…else Statement

    // check if the number is positive or negative/zero

    const number = prompt("Enter a number: ");

    // check if number is greater than 0
    if (number > 0) {
      console.log("The number is positive");
    }
    // if number is not greater than 0
    else {
      console.log("The number is either a negative number or 0");
    }

    console.log("The if...else statement is easy");

[Run Code](/javascript/online-compiler)

**Output 1**

Enter a number: 2
The number is positive
The if...else statement is easy

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

Suppose the user entered **2**. In this case, the condition `number > 0` evaluates to `true`. Hence, the body of the `if` statement is executed and the body of the `else` statement is skipped.

**Output 2**

Enter a number: -1
The number is either a negative number or 0
The if...else statement is easy

Suppose the user entered **\-1**. In this case, the condition `number > 0` evaluates to `false`. Hence, the body of the `else` statement is executed and the body of the `if` statement is skipped.

* * *

JavaScript if...else if statement
---------------------------------

The `if...else` statement is used to execute a block of code among two alternatives. However, if you need to make a choice between more than two alternatives, `if...else if...else` can be used.

The syntax of the `if...else if...else` statement is:

    if (condition1) {
        // code block 1
    } else if (condition2){
        // code block 2
    } else {
        // code block 3
    }

*   If **condition1** evaluates to `true`, the **code block 1** is executed.
*   If **condition1** evaluates to `false`, then **condition2** is evaluated.
    *   If the **condition2** is `true`, the **code block 2** is executed.
    *   If the **condition2** is `false`, the **code block 3** is executed.

![Working of if-else ladder statement in JavaScript](//cdn.programiz.com/sites/tutorial2program/files/js-if-else-if-statement_0.png "Working of if-else if-else statement in JavaScript")

Working of the if...else if...else statement

* * *

### Example 3: if...else if Statement

    // check if the number if positive, negative or zero
    const number = prompt("Enter a number: ");


    // check if number is greater than 0
    if (number > 0) {
        console.log("The number is positive");
    }
    // check if number is 0
    else if (number == 0) {
      console.log("The number is 0");
    }
    // if number is neither greater than 0, nor zero
    else {
        console.log("The number is negative");
    }

    console.log("The if...else if...else statement is easy");

[Run Code](/javascript/online-compiler)

**Output**

Enter a number: 0
The number is 0
The if...else if...else statement is easy

Suppose the user entered **0**, then the first test condition `number > 0` evaluates to `false`. Then, the second test condition `number == 0` evaluates to `true` and its corresponding block is executed.

* * *

Nested if...else Statement
--------------------------

You can also use an `if...else` statement inside of an `if...else` statement. This is known as **nested if...else** statement.

### Example 4: Nested if...else Statement

    // check if the number is positive, negative or zero
    const number = prompt("Enter a number: ");

    if (number >= 0) {
        if (number == 0) {
            console.log("You entered number 0");
        } else {
            console.log("You entered a positive number");
        }
    } else {
        console.log("You entered a negative number");
    }

[Run Code](/javascript/online-compiler)

**Output**

Enter a number: 5
You entered a positive number

Suppose the user entered **5**. In this case, the condition `number >= 0` evaluates to `true`, and the control of the program goes inside the outer `if` statement.

Then, the test condition, `number == 0`, of the inner `if` statement is evaluated. Since it's false, the `else` clause of the inner `if` statement is executed.

**Note:** As you can see, nested `if...else` makes our logic complicated and we should try to avoid using nested `if...else` whenever possible.

* * *

Body of if...else With Only One Statement
-----------------------------------------

If the body of `if...else` has only one statement, we can omit `{ }` in our programs. For example, you can replace

    const number = 2;
    if (number > 0) {
        console.log("The number is positive.");
    } else {
       console.log("The number is negative or zero.");
    }

[Run Code](/javascript/online-compiler)

with

    const number = 2;
    if (number > 0)
        console.log("The number is positive.");
     else
       console.log("The number is negative or zero.");

[Run Code](/javascript/online-compiler)

**Output**

The number is positive.

* * *

More on Decision Making
-----------------------

In certain situations, a ternary operator can replace an `if...else` statement. To learn more, visit [JavaScript Ternary Operator](/javascript/ternary-operator).

If you need to make a choice between more than one alternatives based on a given test condition, the `switch` statement can be used. To learn more, visit [JavaScript switch](https://www.programiz.com/javascript/switch-statement).


JavaScript for loop
===================

In this tutorial, you will learn about the loops and about for loops in JavaScript with the help of examples.

In programming, loops are used to repeat a block of code.

For example, if you want to show a message 100 times, then you can use a loop. It's just a simple example; you can achieve much more with loops.

This tutorial focuses on JavaScript `for` loop. You will learn about the other type of loops in the upcoming tutorials.

* * *

JavaScript for loop
-------------------

The syntax of the `for` loop is:


    for (initialExpression; condition; updateExpression) {
        // for loop body
    }

Here,

1.  The **initialExpression** initializes and/or declares variables and executes only once.
2.  The **condition** is evaluated.
    *   If the condition is `false`, the `for` loop is terminated.
    *   If the condition is `true`, the block of code inside of the `for` loop is executed.
3.  The **updateExpression** updates the value of **initialExpression** when the condition is `true`.
4.  The **condition** is evaluated again. This process continues until the condition is `false`.

To learn more about the **conditions**, visit [JavaScript Comparison and Logical Operators](/javascript/comparison-logical).

* * *

![Working of for loop in JavaScript with flowchart](//cdn.programiz.com/sites/tutorial2program/files/javascript-for-loop.png "Working of for loop in JavaScript")

Flowchart of JavaScript for loop

* * *

### Example 1: Display a Text Five Times

    // program to display text 5 times
    const n = 5;

    // looping from i = 1 to 5
    for (let i = 1; i <= n; i++) {
        console.log(`I love JavaScript.`);
    }

[Run Code](/javascript/online-compiler)

**Output**

I love JavaScript.
I love JavaScript.
I love JavaScript.
I love JavaScript.
I love JavaScript.

Here is how this program works.

Iteration

Variable

Condition: i <= n

Action

1st

`i = 1`
`n = 5`

`true`

I love JavaScript. is printed.
i is increased to **2**.

2nd

`i = 2`
`n = 5`

`true`

I love JavaScript. is printed.
i is increased to **3**.

3rd

`i = 3`
`n = 5`

`true`

I love JavaScript. is printed.
i is increased to **4**.

4th

`i = 4`
`n = 5`

`true`

I love JavaScript. is printed.
i is increased to **5**.

5th

`i = 5`
`n = 5`

`true`

I love JavaScript. is printed.
i is increased to **6**.

6th

`i = 6`
`n = 5`

`false`

The loop is terminated.

* * *

### Example 2: Display Numbers from 1 to 5

    // program to display numbers from 1 to 5
    const n = 5;

    // looping from i = 1 to 5
    // in each iteration, i is increased by 1
    for (let i = 1; i <= n; i++) {
        console.log(i);     // printing the value of i
    }

[Run Code](/javascript/online-compiler)

**Output**

1
2
3
4
5

Here is how this program works.

Iteration

Variable

Condition: i <= n

Action

1st

`i = 1`
`n = 5`

`true`

1 is printed.
i is increased to **2**.

2nd

`i = 2`
`n = 5`

`true`

2 is printed.
i is increased to **3**.

3rd

`i = 3`
`n = 5`

`true`

3 is printed.
i is increased to **4**.

4th

`i = 4`
`n = 5`

`true`

4 is printed.
i is increased to **5**.

5th

`i = 5`
`n = 5`

`true`

5 is printed.
i is increased to **6**.

6th

`i = 6`
`n = 5`

`false`

The loop is terminated.

* * *

### Example 3: Display Sum of n Natural Numbers

    // program to display the sum of natural numbers
    let sum = 0;
    const n = 100

    // looping from i = 1 to n
    // in each iteration, i is increased by 1
    for (let i = 1; i <= n; i++) {
        sum += i;  // sum = sum + i
    }

    console.log('sum:', sum);

[Run Code](/javascript/online-compiler)

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

**Output**

sum: 5050

Here, the value of sum is **0** initially. Then, a `for` loop is iterated from `i = 1 to 100`. In each iteration, i is added to sum and its value is increased by **1**.

When i becomes **101**, the test condition is `false` and sum will be equal to 0 + 1 + 2 + ... + 100.

* * *

The above program to add sum of natural numbers can also be written as

    // program to display the sum of n natural numbers
    let sum = 0;
    const n = 100;

    // looping from i = n to 1
    // in each iteration, i is decreased by 1
    for(let i = n; i >= 1; i-- ) {
        // adding i to sum in each iteration
        sum += i; // sum = sum + i
    }

    console.log('sum:',sum);

[Run Code](/javascript/online-compiler)

This program also gives the same output as the **Example 3**. You can accomplish the same task in many different ways in programming; programming is all about logic.

Although both ways are correct, you should try to make your code more readable.

* * *

### JavaScript Infinite for loop

If the test condition in a `for` loop is always `true`, it runs forever (until memory is full). For example,

    // infinite for loop
    for(let i = 1; i > 0; i++) {
        // block of code
    }

In the above program, the condition is always `true` which will then run the code for infinite times.

* * *

In the next tutorial, you will learn about `while` and `do...while` loop.

JavaScript while and do...while Loop
====================================

In this tutorial, you will learn about while loop and do...while loop with the help of examples.

In programming, loops are used to repeat a block of code. For example, if you want to show a message 100 times, then you can use a loop. It's just a simple example; you can achieve much more with loops.

In the previous tutorial, you learned about the [JavaScript for loop](/javascript/for-loop). Here, you are going to learn about `while` and `do...while` loops.

* * *

JavaScript while Loop
---------------------

The syntax of the `while` loop is:

    while (condition) {
        // body of loop
    }

Here,

1.  A `while` loop evaluates the **condition** inside the parenthesis `()`.
2.  If the **condition** evaluates to `true`, the code inside the `while` loop is executed.
3.  The **condition** is evaluated again.
4.  This process continues until the **condition** is `false`.
5.  When the **condition** evaluates to `false`, the loop stops.

To learn more about the **conditions**, visit [JavaScript Comparison and Logical Operators](/javascript/comparison-logical).

* * *

Flowchart of while Loop
-----------------------

![Flowchart of while loop in JavaScript](//cdn.programiz.com/sites/tutorial2program/files/javascript-while-loop.png "Flowchart of while loop in JavaScript")

Flowchart of JavaScript while loop

* * *

### Example 1: Display Numbers from 1 to 5

    // program to display numbers from 1 to 5
    // initialize the variable
    let i = 1, n = 5;

    // while loop from i = 1 to 5
    while (i <= n) {
        console.log(i);
        i += 1;
    }

[Run Code](/javascript/online-compiler)

**Output**

1
2
3
4
5

Here is how this program works.

Iteration

Variable

Condition: i <= n

Action

1st

`i = 1`
`n = 5`

`true`

1 is printed. i is increased to **2**.

2nd

`i = 2`
`n = 5`

`true`

2 is printed. i is increased to **3**.

3rd

`i = 3`
`n = 5`

`true`

3 is printed. i is increased to **4**.

4th

`i = 4`
`n = 5`

`true`

4 is printed. i is increased to **5**.

5th

`i = 5`
`n = 5`

`true`

5 is printed. i is increased to **6**.

6th

`i = 6`
`n = 5`

`false`

The loop is terminated

* * *

### Example 2: Sum of Positive Numbers Only

    // program to find the sum of positive numbers
    // if the user enters a negative numbers, the loop ends
    // the negative number entered is not added to sum

    let sum = 0;

    // take input from the user
    let number = parseInt(prompt('Enter a number: '));

    while(number >= 0) {

        // add all positive numbers
        sum += number;

        // take input again if the number is positive
        number = parseInt(prompt('Enter a number: '));
    }

    // display the sum
    console.log(`The sum is ${sum}.`);

[Run Code](/javascript/online-compiler)

**Output**

Enter a number: 2
Enter a number: 5
Enter a number: 7
Enter a number: 0
Enter a number: -3
The sum is 14.

In the above program, the user is prompted to enter a number.

Here, `parseInt()` is used because `prompt()` takes input from the user as a string. And when numeric strings are added, it behaves as a string. For example, `'2' + '3' = '23'`. So `parseInt()` converts a numeric string to number.

The `while` loop continues until the user enters a negative number. During each iteration, the number entered by the user is added to the `sum` variable.

When the user enters a negative number, the loop terminates. Finally, the total sum is displayed.

* * *

JavaScript do...while Loop
--------------------------

The syntax of `do...while` loop is:

    do {
        // body of loop
    } while(condition)

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

Here,

1.  The body of the loop is executed at first. Then the **condition** is evaluated.
2.  If the **condition** evaluates to `true`, the body of the loop inside the `do` statement is executed again.
3.  The **condition** is evaluated once again.
4.  If the **condition** evaluates to `true`, the body of the loop inside the `do` statement is executed again.
5.  This process continues until the **condition** evaluates to `false`. Then the loop stops.

**Note**: `do...while` loop is similar to the `while` loop. The only difference is that in `do…while` loop, the body of loop is executed at least once.

* * *

### Flowchart of do...while Loop

![Flowchart of do...while loop in JavaScript](//cdn.programiz.com/sites/tutorial2program/files/javascript-do-while-loop.png "Flowchart of do...while loop in JavaScript")

Flowchart of JavaScript do...while loop

* * *

Let's see the working of `do...while` loop.

### Example 3: Display Numbers from 1 to 5

    // program to display numbers
    let i = 1;
    const n = 5;

    // do...while loop from 1 to 5
    do {
        console.log(i);
        i++;
    } while(i <= n);

[Run Code](/javascript/online-compiler)

**Output**

1
2
3
4
5

Here is how this program works.

Iteration

Variable

Condition: i <= n

Action

 

`i = 1`
`n = 5`

not checked

1 is printed. i is increased to **2**.

1st

`i = 2`
`n = 5`

`true`

2 is printed. i is increased to **3**.

2nd

`i = 3`
`n = 5`

`true`

3 is printed. i is increased to **4**.

3rd

`i = 4`
`n = 5`

`true`

4 is printed. i is increased to **5**.

4th

`i = 5`
`n = 5`

`true`

5 is printed. i is increased to **6**.

5th

`i = 6`
`n = 5`

`false`

The loop is terminated

* * *

### Example 4: Sum of Positive Numbers

    // to find the sum of positive numbers
    // if the user enters negative number, the loop terminates
    // negative number is not added to sum

    let sum = 0;
    let number = 0;

    do {
        sum += number;
        number = parseInt(prompt('Enter a number: '));
    } while(number >= 0)

    console.log(`The sum is ${sum}.`);

[Run Code](/javascript/online-compiler)

**Output 1**

Enter a number: 2
Enter a number: 4
Enter a number: -500
The sum is 6.

Here, the `do...while` loop continues until the user enters a negative number. When the number is negative, the loop terminates; the negative number is not added to the sum variable.

**Output 2**

Enter a number: -80
The sum is 0.

The body of the `do...while` loop runs only once if the user enters a negative number.

* * *

### Infinite while Loop

If **the condition** of a loop is always `true`, the loop runs for infinite times (until the memory is full). For example,

    // infinite while loop
    while(true){
        // body of loop
    }

Here is an example of an infinite `do...while` loop.

    // infinite do...while loop
    const count = 1;
    do {
       // body of loop
    } while(count == 1)

In the above programs, the **condition** is always `true`. Hence, the loop body will run for infinite times.

* * *

for Vs while Loop
-----------------

A `for` loop is usually used when the number of iterations is known. For example,

    // this loop is iterated 5 times
    for (let i = 1; i <=5; ++i) {
       // body of loop
    }

And `while` and `do...while` loops are usually used when the number of iterations are unknown. For example,

    while (condition) {
        // body of loop
    }

JavaScript break Statement
==========================

In this tutorial, you will learn about the break statement with the help of examples.

The `break` statement is used to terminate the loop immediately when it is encountered.

The syntax of the `break` statement is:

    break [label];

**Note:** `label` is optional and rarely used.

* * *

Working of JavaScript break Statement
-------------------------------------

![Working of break statement in JavaScript](//cdn.programiz.com/sites/tutorial2program/files/javascript-break-statement.png "Working of break statement in JavaScript")

Working of JavaScript break Statement

* * *

Example 1: break with for Loop
------------------------------

    // program to print the value of i
    for (let i = 1; i <= 5; i++) {
        // break condition
        if (i == 3) {
            break;
        }
        console.log(i);
    }

[Run Code](/javascript/online-compiler)

**Output**

1
2

In the above program, the `for` loop is used to print the value of i in each iteration. The `break` statement is used as:

    if(i == 3) {
        break;
    }

This means, when i is equal to **3**, the `break` statement terminates the loop. Hence, the output doesn't include values greater than or equal to 3.

**Note**: The `break` statement is almost always used with decision-making statements. To learn more, visit [JavaScript if...else Statement](/javascript/if-else).

To learn more about `for` loop, visit [JavaScript for loop](/javascript/for-loop).

* * *

Example 2: break with while Loop
--------------------------------

    // program to find the sum of positive numbers
    // if the user enters a negative numbers, break ends the loop
    // the negative number entered is not added to sum

    let sum = 0, number;

    while(true) {

        // take input again if the number is positive
        number = parseInt(prompt('Enter a number: '));

        // break condition
        if(number < 0) {
            break;
        }

        // add all positive numbers
        sum += number;

    }

    // display the sum
    console.log(`The sum is ${sum}.`);

[Run Code](/javascript/online-compiler)

**Output**

Enter a number: 1
Enter a number: 2
Enter a number: 3
Enter a number: -5
The sum is 6.

In the above program, the user enters a number. The `while` loop is used to print the total sum of numbers entered by the user.

Here the `break` statement is used as:

    if(number < 0) {
        break;
    }

When the user enters a negative number, here \-5, the `break` statement terminates the loop and the control flow of the program goes outside the loop.

Thus, the `while` loop continues until the user enters a negative number.

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

To learn more about `while` loop, visit [JavaScript while loop](/javascript/while-loop).

* * *

break with Nested Loop
----------------------

When `break` is used inside of two nested loops, `break` terminates the inner loop. For example,

    // nested for loops

    // first loop
    for (let i = 1; i <= 3; i++) {

        // second loop
        for (let j = 1; j <= 3; j++) {
            if (i == 2) {
              break;
            }
            console.log(`i = ${i}, j = ${j}`);
        }
    }

[Run Code](/javascript/online-compiler)

**Output**

i = 1, j = 1
i = 1, j = 2
i = 1, j = 3
i = 3, j = 1
i = 3, j = 2
i = 3, j = 3

In the above program, when `i == 2`, `break` statement executes. It terminates the inner loop and control flow of the program moves to the outer loop.

Hence, the value of i = 2 is never displayed in the output.

* * *

JavaScript Labeled break
------------------------

When using nested loops, you can also terminate the outer loop with a `label` statement.

However labeled `break` is rarely used in JavaScript because this makes the code harder to read and understand.

If you want to learn more about the labeled break statements, visit [labeled break.](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label)

* * *

The `break` statement is also used with `switch` statements. To learn more, visit [JavaScript switch statement.](/javascript/switch-statement)

JavaScript continue Statement
=============================

In this tutorial, you will learn about the continue statement with the help of examples.

The `continue` statement is used to skip the current iteration of the loop and the control flow of the program goes to the next iteration.

The syntax of the `continue` statement is:

    continue [label];

**Note:** `label` is optional and rarely used.

* * *

Working of JavaScript continue Statement
----------------------------------------

![Working of continue statement in JavaScript](//cdn.programiz.com/sites/tutorial2program/files/working-javascript-continue-statement.png "Working of continue statement in JavaScript")

Working of JavaScript continue Statement

* * *

continue with for Loop
----------------------

In a `for` loop, `continue` skips the current iteration and control flow jumps to the **updateExpression**.

* * *

### Example 1: Print the Value of i

    // program to print the value of i
    for (let i = 1; i <= 5; i++) {

        // condition to continue
        if (i == 3) {
            continue;
        }

        console.log(i);
    }

[Run Code](/javascript/online-compiler)

**Output**

1
2
4
5

In the above program, `for` loop is used to print the value of i in each iteration.

Notice the `continue` statement inside the loop.

    if(i == 3) {
        continue;
    }

This means

*   When i is equal to **3**, the `continue` statement skips the third iteration.
*   Then, `i` becomes **4** and the test **condition** and `continue` statement is evaluated again.
*   Hence, **4** and **5** are printed in the next two iterations.

**Note**: The `continue` statement is almost always used with decision making statements. To learn more, visit [JavaScript if...else Statement](/javascript/if-else).

To learn more about `for` loop, visit [JavaScript for loop](/javascript/for-loop).

**Note**: The `break` statement terminates the loop entirely. However, the `continue` statement only skips the current iteration.

* * *

continue with while Loop
------------------------

In a `while` loop, `continue` skips the current iteration and control flow of the program jumps back to the `while` condition.

The `continue` statement works in the same way for `while` and `do...while` loops.

* * *

### Example 2: Calculate Positive Number

    // program to calculate positive numbers only
    // if the user enters a negative number, that number is skipped from calculation

    // negative number -> loop terminate
    // non-numeric character -> skip iteration

    let sum = 0;
    let number = 0;

    while (number >= 0) {

        // add all positive numbers
        sum += number;

        // take input from the user
        number = parseInt(prompt('Enter a number: '));

        // continue condition
        if (isNaN(number)) {
            console.log('You entered a string.');
            number = 0; // the value of number is made 0 again
            continue;
        }

    }

    // display the sum
    console.log(`The sum is ${sum}.`);

[Run Code](/javascript/online-compiler)

**Output**

Enter a number: 1
Enter a number: 2
Enter a number: hello
You entered a string.
Enter a number: 5
Enter a number: -2
The sum is 8.

In the above program, the user enters a number. The `while` loop is used to print the total sum of positive numbers entered by the user.

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

Notice the use of the `continue` statement.

    if (isNaN(number)) {
        continue;
    }

*   When the user enters a non-numeric number/string, the `continue` statement skips the current iteration. Then the control flow of the program goes to the **condition** of `while` loop.
*   When the user enters a number less than **0**, the loop terminates.

In the above program, `isNaN()` is used to check if the value entered by a user is a number or not.

To learn more about the `while` loop, visit [JavaScript while loop](/javascript/while-loop).

* * *

continue with Nested Loop
-------------------------

When `continue` is used inside of two nested loops, `continue` skips the current iteration of the inner loop. For example,

    // nested for loops

    // first loop
    for (let i = 1; i <= 3; i++) {

        // second loop
        for (let j = 1; j <= 3; j++) {
            if (j == 2) {
              continue;
            }
            console.log(`i = ${i}, j = ${j}`);
        }
    }

[Run Code](/javascript/online-compiler)

**Output**

i = 1, j = 1
i = 1, j = 3
i = 2, j = 1
i = 2, j = 3
i = 3, j = 1
i = 3, j = 3

In the above program, when the `continue` statement executes, it skips the current iteration in the inner loop and control flow of the program moves to the **updateExpression** of the inner loop.

Hence, the value of j = 2 is never displayed in the output.

* * *

JavaScript Labeled continue
---------------------------

When using nested loops, you can skip the current iteration and the control flow of the program can be passed to a `label` statement's **updateExpression**.

But labeled `continue` is rarely used in JavaScript because this makes the code harder to read and understand.

If you want to learn more about the labeled continue statements, visit [labeled continue](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label).

JavaScript Switch Statement
===========================

In this tutorial, you will learn about the JavaScript switch statement with the help of examples.

The JavaScript `switch` statement is used in decision making.

The `switch` statement evaluates an expression and executes the corresponding body that matches the expression's result.

The syntax of the `switch` statement is:

    switch(variable/expression) {
        case value1:
            // body of case 1
            break;

        case value2:
            // body of case 2
            break;

        case valueN:
            // body of case N
            break;

        default:
            // body of default
    }

The `switch` statement evaluates a variable/expression inside parentheses `()`.

*   If the result of the expression is equal to `value1`, its body is executed.
*   If the result of the expression is equal to `value2`, its body is executed.
*   This process goes on. If there is no matching case, the `default` body executes.

**Notes:**

*   The `break` statement is optional. If the break statement is encountered, the switch statement ends.
*   If the `break` statement is not used, the cases after the matching case are also executed.
*   The `default` clause is also optional.

* * *

Flowchart of switch Statement
-----------------------------

![Flowchart of JavaScript switch statement](//cdn.programiz.com/sites/tutorial2program/files/javascript-switch-statement.png "Flowchart of JavaScript switch statement")

Flowchart of JavaScript switch statement

* * *

### Example 1: Simple Program Using switch Statement

    // program using switch statement
    let a = 2;

    switch (a) {

        case 1:
            a = 'one';
            break;
        case 2:
            a = 'two';
            break;
        default:
            a = 'not found';
            break;
    }
    console.log(`The value is ${a}`);

[Run Code](/javascript/online-compiler)

**Output**

The value is two.

In the above program, an expression `a = 2` is evaluated with a `switch` statement.

*   The **expression's** result is evaluated with `case 1` which results in `false`.
*   Then the `switch` statement goes to the second case. Here, the **expression's** result matches with `case 2`. So The value is two is displayed.
*   The `break` statement terminates the block and control flow of the program jumps to outside of the `switch` block.

* * *

### Example 2: Type Checking in switch Statement

    // program using switch statement
    let a = 1;

    switch (a) {
        case "1":
            a = 1;
            break;
        case 1:
            a = 'one';
            break;
        case 2:
            a = 'two';
            break;

        default:
            a = 'not found';
            break;
    }
    console.log(`The value is ${a}`);

[Run Code](/javascript/online-compiler)

**Output**

The value is one.

In the above program, an expression `a = 1` is evaluated with a `switch` statement.

*   In JavaScript, the switch statement checks the value strictly. So the expression's result does not match with `case "1"`.
*   Then the `switch` statement goes to the second case. Here, the expressions's result matches with `case 1`. So The value is one is displayed.
*   The `break` statement terminates the block and control flow of the program jumps to outside of the `switch` block.

**Note**: In JavaScript, the switch statement checks the cases strictly (should be of the same data type) with the expression's result. Notice in the above example, **1** does not match with **"1"**.

* * *

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

Let's write a program to make a simple calculator with the `switch` statement.

### Example 3: Simple Calculator

    // program for a simple calculator
    let result;

    // take the operator input
    const operator = prompt('Enter operator ( either +, -, * or / ): ');

    // take the operand input
    const number1 = parseFloat(prompt('Enter first number: '));
    const number2 = parseFloat(prompt('Enter second number: '));

    switch(operator) {
        case '+':
            result = number1 + number2;
            console.log(`${number1} + ${number2} = ${result}`);
            break;
        case '-':
            result = number1 - number2;
            console.log(`${number1} - ${number2} = ${result}`);
            break;
        case '*':
            result = number1 * number2;
            console.log(`${number1} * ${number2} = ${result}`);
            break;
        case '/':
            result = number1 / number2;
            console.log(`${number1} / ${number2} = ${result}`);
            break;

        default:
            console.log('Invalid operator');
            break;
    }

[Run Code](/javascript/online-compiler)

**Output**

Enter operator: +
Enter first number: 4
Enter second number: 5
4 + 5 = 9

In above program, the user is asked to enter either **+**, **\-**, **\*** or /, and two operands. Then, the `switch` statement executes cases based on the user input.

* * *

JavaScript switch With Multiple Case
------------------------------------

In a JavaScript switch statement, cases can be grouped to share the same code.

### Example 4: switch With Multiple Case

    // multiple case switch program
    let fruit = 'apple';
    switch(fruit) {
        case 'apple':
        case 'mango':
        case 'pineapple':
            console.log(`${fruit} is a fruit.`);
            break;
        default:
            console.log(`${fruit} is not a fruit.`);
            break;
    }

[Run Code](/javascript/online-compiler)

**Output**

apple is a fruit.

In the above program, multiple cases are grouped. All the grouped cases share the same code.

If the value of the fruit variable had value `mango` or `pineapple`, the output would have been the same.

* * *

**Recommended articles**

*   [JavaScript switch Without break](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/switch#What_happens_if_I_forgot_a_break)
*   [Switch Vs if...else Statement](https://stackoverflow.com/questions/2922948/javascript-switch-vs-if-else-if-else)

JavaScript Function and Function Expressions
============================================

In this tutorial, you will learn about JavaScript function and function expressions with the help of examples.

JavaScript Function
-------------------

A function is a block of code that performs a specific task.

Suppose you need to create a program to create a circle and color it. You can create two functions to solve this problem:

*   a function to draw the circle
*   a function to color the circle

Dividing a complex problem into smaller chunks makes your program easy to understand and reusable.

JavaScript also has a huge number of inbuilt functions. For example, `Math.sqrt()` is a function to calculate the square root of a number.

In this tutorial, you will learn about user-defined functions.

* * *

### Declaring a Function

The syntax to declare a function is:

    function nameOfFunction () {
        // function body
    }

*   A function is declared using the `function` keyword.
*   The basic rules of naming a function are similar to naming a variable. It is better to write a descriptive name for your function. For example, if a function is used to add two numbers, you could name the function `add` or `addNumbers`.
*   The body of function is written within `{}`.

For example,

    // declaring a function named greet()
    function greet() {
        console.log("Hello there");
    }

* * *

### Calling a Function

In the above program, we have declared a function named `greet()`. To use that function, we need to call it.

Here's how you can call the above `greet()` function.

    // function call
    greet();

* * *

![Working of JavaScript function](//cdn.programiz.com/cdn/farfuture/NdxxeWlRfoHMPgdcWPkeVy1wN9MwAgoqoYqZkFQDMFQ/mtime:1591592059/sites/tutorial2program/files/javascript-function-example1.png "Working of JavaScript function")

Working of a Function in JavaScript

* * *

### Example 1: Display a Text

    // program to print a text
    // declaring a function
    function greet() {
        console.log("Hello there!");
    }

    // calling the function
    greet();

[Run Code](/javascript/online-compiler)

**Output**

Hello there!

* * *

### Function Parameters

A function can also be declared with parameters. A parameter is a value that is passed when declaring a function.

![Working of JavaScript Function with parameter](//cdn.programiz.com/cdn/farfuture/oAZVf3IqOKOYj_aJ-IoYQvbJ2CB-B3y4HXSLXBUmYcY/mtime:1591592163/sites/tutorial2program/files/javascript-function-with-parameter.png "Working of JavaScript Function with parameter")

Working of JavaScript Function with parameter

* * *

### Example 2: Function with Parameters

    // program to print the text
    // declaring a function
    function greet(name) {
        console.log("Hello " + name + ":)");
    }

    // variable name can be different
    let name = prompt("Enter a name: ");

    // calling function
    greet(name);

[Run Code](/javascript/online-compiler)

**Output**

Enter a name: Simon
Hello Simon :)

In the above program, the `greet` function is declared with a `name` parameter. The user is prompted to enter a name. Then when the function is called, an argument is passed into the function.

**Note**: When a value is passed when declaring a function, it is called **parameter**. And when the function is called, the value passed is called **argument**.

* * *

### Example 3: Add Two Numbers

    // program to add two numbers using a function
    // declaring a function
    function add(a, b) {
        console.log(a + b);
    }

    // calling functions
    add(3,4);
    add(2,9);

[Run Code](/javascript/online-compiler)

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

**Output**

7
11

In the above program, the `add` function is used to find the sum of two numbers.

*   The function is declared with two parameters `a` and `b`.
*   The function is called using its name and passing two arguments **3** and **4** in one and **2** and **9** in another.

Notice that you can call a function as many times as you want. You can write one function and then call it multiple times with different arguments.

* * *

### Function Return

The `return` statement can be used to return the value to a function call.

The `return` statement denotes that the function has ended. Any code after `return` is not executed.

If nothing is returned, the function returns an `undefined` value.

![Working of JavaScript Function with return statement](//cdn.programiz.com/cdn/farfuture/b4h4Zo5ZYxj-EyfQyao-J5TqbKEefFgqqusPGLWPFS0/mtime:1591786573/sites/tutorial2program/files/javascript-return-statement.png "Working of JavaScript Function with return statement")

Working of JavaScript Function with return statement

* * *

### Example 4: Sum of Two Numbers

    // program to add two numbers
    // declaring a function
    function add(a, b) {
        return a + b;
    }

    // take input from the user
    let number1 = parseFloat(prompt("Enter first number: "));
    let number2 = parseFloat(prompt("Enter second number: "));

    // calling function
    let result = add(number1,number2);

    // display the result
    console.log("The sum is " + result);

[Run Code](/javascript/online-compiler)

**Output**

Enter first number: 3.4
Enter second number: 4
The sum is 7.4

In the above program, the sum of the numbers is returned by the function using the `return` statement. And that value is stored in the result variable.

* * *

### Benefits of Using a Function

*   Function makes the code reusable. You can declare it once and use it multiple times.
*   Function makes the program easier as each small task is divided into a function.
*   Function increases readability.

* * *

Function Expressions
--------------------

In Javascript, functions can also be defined as expressions. For example,

    // program to find the square of a number
    // function is declared inside the variable
    let x = function (num) { return num * num };
    console.log(x(4));

    // can be used as variable value for other variables
    let y = x(3);
    console.log(y);

[Run Code](/javascript/online-compiler)

**Output**

16
9

In the above program, variable x is used to store the function. Here the function is treated as an expression. And the function is called using the variable name.

The function above is called an anonymous function.

**Note:** In ES2015, JavaScript expressions are written as arrow functions. You will learn about them in later tutorials.

JavaScript Variable Scope
=========================

In this tutorial, you will learn about variable scope in JavaScript with the help of examples.

Scope refers to the availability of variables and functions in certain parts of the code.

In JavaScript, a variable has two types of scope:

1.  Global Scope
2.  Local Scope

* * *

Global Scope
------------

A variable declared at the top of a program or outside of a function is considered a global scope variable.

Let's see an example of a global scope variable.

    // program to print a text
    let a = "hello";

    function greet () {
        console.log(a);
    }

    greet(); // hello

[Run Code](/javascript/online-compiler)

In the above program, variable a is declared at the top of a program and is a global variable. It means the variable `a` can be used anywhere in the program.

* * *

The value of a global variable can be changed inside a function. For example,

    // program to show the change in global variable
    let a = "hello";

    function greet() {
        a = 3;
    }

    // before the function call
    console.log(a);

    //after the function call
    greet();
    console.log(a); // 3

[Run Code](/javascript/online-compiler)

In the above program, variable a is a global variable. The value of a is hello. Then the variable a is accessed inside a function and the value changes to **3.**

Hence, the value of a changes after changing it inside the function.

**Note**: It is a good practice to avoid using global variables because the value of a global variable can change in different areas in the program. It can introduce unknown results in the program.

* * *

In JavaScript, a variable can also be used without declaring it. If a variable is used without declaring it, that variable automatically becomes a global variable.

For example,

    function greet() {
        a = "hello"
    }

    greet();

    console.log(a); // hello

[Run Code](/javascript/online-compiler)

In the above program, variable a is a global variable.

If the variable was declared using `let a = "hello"`, the program would throw an error.

**Note**: In JavaScript, there is `"strict mode";` in which a variable cannot be used without declaring it. To learn more about strict, visit [JavaScript Strict](https://www.programiz.com/javascript/use-strict).

* * *

Local Scope
-----------

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

A variable can also have a local scope, i.e it can only be accessed within a function.

### Example 1: Local Scope Variable

    // program showing local scope of a variable
    let a = "hello";

    function greet() {
        let b = "World"
        console.log(a + b);
    }

    greet();
    console.log(a + b); // error

[Run Code](/javascript/online-compiler)

**Output**

helloWorld
Uncaught ReferenceError: b is not defined

In the above program, variable a is a global variable and variable b is a local variable. The variable b can be accessed only inside the function greet. Hence, when we try to access variable b outside of the function, an error occurs.

* * *

### let is Block Scoped

The `let` keyword is block-scoped (variable can be accessed only in the immediate block).

### Example 2: block-scoped Variable

    // program showing block-scoped concept
    // global variable
    let a = 'Hello';

    function greet() {

        // local variable
        let b = 'World';

        console.log(a + ' ' + b);

        if (b == 'World') {

            // block-scoped variable
            let c = 'hello';

            console.log(a + ' ' + b + ' ' + c);
        }

        // variable c cannot be accessed here
        console.log(a + ' ' + b + ' ' + c);
    }

    greet();

[Run Code](/javascript/online-compiler)

**Output**

Hello World
Hello World hello
Uncaught ReferenceError: c is not defined

In the above program, variable

*   a is a global variable. It can be accessed anywhere in the program.
*   b is a local variable. It can be accessed only inside the function `greet`.
*   c is a block-scoped variable. It can be accessed only inside the `if` statement block.

Hence, in the above program, the first two `console.log()` work without any issue.

However, we are trying to access the block-scoped variable c outside of the block in the third `console.log()`. This will throw an error.

* * *

**Note**: In JavaScript, `var` is function scoped and `let` is block-scoped. If you try to use `var c = 'hello';` inside the `if` statement in the above program, the whole program works, as c is treated as a local variable.

To learn more about `let` versus `var`, visit [JavaScript let vs var](https://www.programiz.com/javascript/let-vs-var).

JavaScript Hoisting
===================

In this tutorial, you will learn about JavaScript hoisting with the help of examples.

**Hoisting** in JavaScript is a behavior in which a function or a variable can be used before declaration. For example,

    // using test before declaring
    console.log(test);   // undefined
    var test;

[Run Code](/javascript/online-compiler)

The above program works and the output will be undefined. The above program behaves as

    // using test before declaring
    var test;
    console.log(test); // undefined

[Run Code](/javascript/online-compiler)

Since the variable test is only declared and has no value, `undefined` value is assigned to it.

If you want to learn more about variables, visit [JavaScript Variables](/javascript/variables-constants).

**Note**: In hoisting, though it seems that the declaration has moved up in the program, the actual thing that happens is that the function and variable declarations are added to memory during the compile phase.

* * *

Variable Hoisting
-----------------

In terms of variables and constants, keyword `var` is hoisted and `let` and `const` does not allow hoisting.

For example,

    // program to display value
    a = 5;
    console.log(a);
    var a; // 5

[Run Code](/javascript/online-compiler)

In the above example, variable a is used before declaring it. And the program works and displays the output 5. The program behaves as:

    // program to display value
    var a;
    a = 5;
    console.log(a); // 5

[Run Code](/javascript/online-compiler)

* * *

However in JavaScript, initializations are not hoisted. For example,

    // program to display value
    console.log(a);
    var a = 5;

[Run Code](/javascript/online-compiler)

**Output**

undefined

The above program behaves as:

    var a;
    console.log(a);
    a = 5;

[Run Code](/javascript/online-compiler)

Only the declaration is moved to the memory in the compile phase. Hence, the value of variable a is `undefined` because a is printed without initializing it.

* * *

Also, when the variable is used inside the function, the variable is hoisted only to the top of the function. For example,

    // program to display value
    var a = 4;

    function greet() {
        b = 'hello';
        console.log(b); // hello
        var b;
    }

    greet(); // hello
    console.log(b);

[Run Code](/javascript/online-compiler)

**Output**

hello
Uncaught ReferenceError: b is not defined

In the above example, variable b is hoisted to the top of the function `greet` and becomes a local variable. Hence b is only accessible inside the function. b does not become a global variable.

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

To learn more about local and global variables, visit [JavaScript Variable Scope](https://www.programiz.com/javascript/variable-scope).

**Note**: In hoisting, the variable declaration is only accessible to the immediate scope.

* * *

If a variable is used with the `let` keyword, that variable is not hoisted. For example,

    // program to display value
    a = 5;
    console.log(a);
    let a; // error

[Run Code](/javascript/online-compiler)

**Output**

Uncaught ReferenceError: Cannot access 'a' before initialization

While using `let`, the variable must be declared first.

* * *

Function Hoisting
-----------------

A function can be called before declaring it. For example,

    // program to print the text
    greet();

    function greet() {
        console.log('Hi, there.');
    }

[Run Code](/javascript/online-compiler)

**Output**

Hi, there

In the above program, the function `greet` is called before declaring it and the program shows the output. This is due to hoisting.

* * *

However, when a function is used as an **expression**, an error occurs because only declarations are hoisted. For example;

    // program to print the text
    greet();

    let greet = function() {
        console.log('Hi, there.');
    }

[Run Code](/javascript/online-compiler)

**Output**

Uncaught ReferenceError: greet is not defined

If `var` was used in the above program, the error would be:

Uncaught TypeError: greet is not a function

* * *

**Note**: Generally, hoisting is not performed in other programming languages like Python, C, C++, Java.

Hoisting can cause undesirable outcomes in your program. And it is best to declare variables and functions first before using them and avoid hoisting.

In the case of variables, it is better to use `let` than `var`.

JavaScript Recursion
====================

In this tutorial, you will learn about recursion in JavaScript with the help of examples.

Recursion is a process of calling itself. A function that calls itself is called a recursive function.

The syntax for recursive function is:

    function recurse() {
        // function code
        recurse();
        // function code
    }

    recurse();

Here, the `recurse()` function is a recursive function. It is calling itself inside the function.

![Working of recursion in JavaScript](//cdn.programiz.com/sites/tutorial2program/files/javascript-recursion.png "Working of recursion in JavaScript")

Working of recursion in JavaScript

A recursive function must have a condition to stop calling itself. Otherwise, the function is called indefinitely.

Once the condition is met, the function stops calling itself. This is called a base condition.

To prevent infinite recursion, you can use [if...else statement](/javascript/if-else) (or similar approach) where one branch makes the recursive call, and the other doesn't.

So, it generally looks like this.

    function recurse() {
        if(condition) {
            recurse();
        }
        else {
            // stop calling recurse()
        }
    }

    recurse();

* * *

A simple example of a recursive function would be to count down the value to 1.

Example 1: Print Numbers
------------------------

    // program to count down numbers to 1
    function countDown(number) {

        // display the number
        console.log(number);

        // decrease the number value
        const newNumber = number - 1;

        // base case
        if (newNumber > 0) {
            countDown(newNumber);
        }
    }

    countDown(4);

[Run Code](/javascript/online-compiler)

**Output**

4
3
2
1

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

In the above program, the user passes a number as an argument when calling a function.

In each iteration, the number value is decreased by **1** and function `countDown()` is called until the number is positive. Here, `newNumber > 0` is the base condition.

This recursive call can be explained in the following steps:

countDown(4) prints 4 and calls countDown(3)
countDown(3) prints 3 and calls countDown(2)
countDown(2) prints 2 and calls countDown(1)
countDown(1) prints 1 and calls countDown(0)

When the number reaches **0**, the base condition is met, and the function is not called anymore.

* * *

Example 2: Find Factorial
-------------------------

    // program to find the factorial of a number
    function factorial(x) {

        // if number is 0
        if (x === 0) {
            return 1;
        }

        // if number is positive
        else {
            return x * factorial(x - 1);
        }
    }

    const num = 3;

    // calling factorial() if num is non-negative
    if (num > 0) {
        let result = factorial(num);
        console.log(`The factorial of ${num} is ${result}`);
    }

[Run Code](/javascript/online-compiler)

**Output**

The factorial of 3 is 6

When you call function `factorial()` with a positive integer, it will recursively call itself by decreasing the number.

This process continues until the number becomes **1**. Then when the number reaches **0**, **1** is returned.

![Working of recursive function to calculate factorial](//cdn.programiz.com/sites/tutorial2program/files/javascript-factorial-working.png "Working of JavaScript recursion in Factorial")

Computing Factorial Using Recursion

This recursive call can be explained in the following steps:

factorial(3) returns 3 \* factorial(2)
factorial(2) returns 3 \* 2 \* factorial(1)
factorial(1) returns 3 \* 2 \* 1 \* factorial(0)
factorial(0) returns 3 \* 2 \* 1 \* 1
JavaScript Objects
==================

In this tutorial, you will learn about JavaScript objects with the help of examples.

In the [JavaScript data types](/javascript/data-types) tutorial, you learned about 7 different primitive data types. And here, you are going to learn about the eighth data-type (JavaScript object).

JavaScript object is a non-primitive data-type that allows you to store multiple collections of data.

**Note**: If you are familiar with other programming languages, JavaScript objects are a bit different. You do not need to create classes in order to create objects.

Here is an example of a JavaScript object.

    // object
    const student = {
        firstName: 'ram',
        class: 10
    };

Here, `student` is an object that stores values such as strings and numbers.

* * *

JavaScript Object Declaration
-----------------------------

The syntax to declare an object is:

    const object_name = {
       key1: value1,
       key2: value2
    }

Here, an object `object_name` is defined. Each member of an object is a **key: value** pair separated by commas and enclosed in curly braces `{}`.

For example,

    // object creation
    const person = {
        name: 'John',
        age: 20
    };
    console.log(typeof person); // object

[Run Code](/javascript/online-compiler)

You can also define an object in a single line.

    const person = { name: 'John', age: 20 };

In the above example, `name` and `age` are keys, and `John` and `20` are values respectively.

There are other ways to declare an object in JavaScript. To learn more, visit [Different Ways to Declare JavaScript Objects](https://www.programiz.com/javascript/examples/create-object).

* * *

JavaScript Object Properties
----------------------------

In JavaScript, "key: value" pairs are called **properties**. For example,

    let person = {
        name: 'John',
        age: 20
    };

Here, `name: 'John'` and `age: 20` are properties.

![Example of JavaScript object properties](//cdn.programiz.com/sites/tutorial2program/files/javascript-object-properties.png "Example of JavaScript object properties")

JavaScript object properties

* * *

Accessing Object Properties
---------------------------

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

You can access the **value** of a property by using its **key**.

### 1\. Using dot Notation

Here's the syntax of the dot notation.

    objectName.key

For example,

    const person = {
        name: 'John',
        age: 20,
    };

    // accessing property
    console.log(person.name); // John

[Run Code](/javascript/online-compiler)

* * *

### 2\. Using bracket Notation

Here is the syntax of the bracket notation.

    objectName["propertyName"]

For example,

    const person = {
        name: 'John',
        age: 20,
    };

    // accessing property
    console.log(person["name"]); // John

[Run Code](/javascript/online-compiler)

* * *

JavaScript Nested Objects
-------------------------

An object can also contain another object. For example,

    // nested object
    const student = {
        name: 'John',
        age: 20,
        marks: {
            science: 70,
            math: 75
        }
    }

    // accessing property of student object
    console.log(student.marks); // {science: 70, math: 75}

    // accessing property of marks object
    console.log(student.marks.science); // 70

[Run Code](/javascript/online-compiler)

In the above example, an object `student` contains an object value in the `marks` property.

* * *

JavaScript Object Methods
-------------------------

In JavaScript, an object can also contain a function. For example,

    const person = {
        name: 'Sam',
        age: 30,
        // using function as a value
        greet: function() { console.log('hello') }
    }

    person.greet(); // hello

[Run Code](/javascript/online-compiler)

Here, a function is used as a value for the greet key. That's why we need to use `person.greet()` instead of `person.greet` to call the function inside the object.

A JavaScript **method** is a property containing a function declaration. In the next tutorial, you will learn about [JavaScript Methods](https://www.programiz.com/javascript/methods) in detail.

JavaScript Methods and this Keyword
===================================

In this tutorial, you will learn about JavaScript object methods and this keyword with the help of examples.

In JavaScript, objects can also contain functions. For example,

    // object containing method
    const person = {
        name: 'John',
        greet: function() { console.log('hello'); }
    };

[Run Code](/javascript/online-compiler)

In the above example, a `person` object has two keys (`name` and `greet`), which have a string value and a function value, respectively.

Hence basically, the JavaScript **method** is an object property that has a function value.

* * *

Accessing Object Methods
------------------------

You can access an object method using a dot notation. The syntax is:

    objectName.methodKey()

You can access property by calling an **objectName** and a **key**. You can access a method by calling an **objectName** and a **key** for that method along with `()`. For example,

    // accessing method and property
    const person = {
        name: 'John',
        greet: function() { console.log('hello'); }
    };

    // accessing property
    person.name; // John

    // accessing method
    person.greet(); // hello

[Run Code](/javascript/online-compiler)

Here, the `greet` method is accessed as `person.greet()` instead of `person.greet`.

If you try to access the method with only `person.greet`, it will give you a function definition.

    person.greet; // ƒ () { console.log('hello'); }

JavaScript Built-In Methods
---------------------------

In JavaScript, there are many built-in methods. For example,

    let number = '23.32';
    let result = parseInt(number);

    console.log(result); // 23

[Run Code](/javascript/online-compiler)

Here, the `parseInt()` method of Number object is used to convert numeric string value to an integer value.

To learn more about built-in methods, visit [JavaScript Built-In Methods](https://www.programiz.com/javascript/library).

* * *

Adding a Method to a JavaScript Object
--------------------------------------

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

You can also add a method in an object. For example,

    // creating an object
    let student = { };

    // adding a property
    student.name = 'John';

    // adding a method
    student.greet = function() {
        console.log('hello');
    }

    // accessing a method
    student.greet(); // hello

[Run Code](/javascript/online-compiler)

In the above example, an empty `student` object is created. Then, the `name` property is added. Similarly, the `greet` method is also added. In this way, you can add a method as well as property to an object.

* * *

JavaScript this Keyword
-----------------------

To access a property of an object from within a method of the same object, you need to use the `this` keyword. Let's consider an example.

    const person = {
        name: 'John',
        age: 30,

        // accessing name property by using this.name
        greet: function() { console.log('The name is' + ' ' + this.name); }
    };

    person.greet();

[Run Code](/javascript/online-compiler)

**Output**

The name is John

In the above example, a `person` object is created. It contains properties (`name` and `age`) and a method `greet`.

In the method `greet`, while accessing a property of an object, `this` keyword is used.

In order to access the **properties** of an object, `this` keyword is used following by `.` and **key**.

**Note**: In JavaScript, `this` keyword when used with the object's method refers to the object. `this` is bound to an object.

* * *

However, the function inside of an object can access it's variable in a similar way as a normal function would. For example,

    const person = {
        name: 'John',
        age: 30,
        greet: function() {
            let surname = 'Doe';
            console.log('The name is' + ' ' + this.name + ' ' + surname); }
    };

    person.greet();

[Run Code](/javascript/online-compiler)

**Output**

The name is John Doe
JavaScript Constructor Function
===============================

In this tutorial, you will learn about JavaScript constructor function with the help of examples.

In JavaScript, a constructor function is used to create objects. For example,

    // constructor function
    function Person () {
        this.name = 'John',
        this.age = 23
    }

    // create an object
    const person = new Person();

[Run Code](/javascript/online-compiler)

In the above example, `function Person()` is an object constructor function.

To create an object from a constructor function, we use the `new` keyword.

**Note**: It is considered a good practice to capitalize the first letter of your constructor function.

* * *

Create Multiple Objects with Constructor Function
-------------------------------------------------

In JavaScript, you can create multiple objects from a constructor function. For example,

    // constructor function
    function Person () {
        this.name = 'John',
        this.age = 23,

         this.greet = function () {
            console.log('hello');
        }
    }

    // create objects
    const person1 = new Person();
    const person2 = new Person();

    // access properties
    console.log(person1.name);  // John
    console.log(person2.name);  // John

[Run Code](/javascript/online-compiler)

In the above program, two objects are created using the same constructor function.

* * *

JavaScript this Keyword
-----------------------

In JavaScript, when `this` keyword is used in a constructor function, `this` refers to the object when the object is created. For example,

    // constructor function
    function Person () {
        this.name = 'John',
    }

    // create object
    const person1 = new Person();

    // access properties
    console.log(person1.name);  // John

[Run Code](/javascript/online-compiler)

Hence, when an object accesses the properties, it can directly access the property as `person1.name`.

* * *

JavaScript Constructor Function Parameters
------------------------------------------

You can also create a constructor function with parameters. For example,

    // constructor function
    function Person (person_name, person_age, person_gender) {

       // assigning  parameter values to the calling object
        this.name = person_name,
        this.age = person_age,
        this.gender = person_gender,

        this.greet = function () {
            return ('Hi' + ' ' + this.name);
        }
    }


    // creating objects
    const person1 = new Person('John', 23, 'male');
    const person2 = new Person('Sam', 25, 'female');

    // accessing properties
    console.log(person1.name); // "John"
    console.log(person2.name); // "Sam"


[Run Code](/javascript/online-compiler)

In the above example, we have passed arguments to the constructor function during the creation of the object.

    const person1 = new Person('John', 23, 'male');
    const person2 = new Person('Sam', 25, 'male');

This allows each object to have different properties. As shown above,

`console.log(person1.name);` gives John

`console.log(person2.name);` gives Sam

* * *

Create Objects: Constructor Function Vs Object Literal
------------------------------------------------------

*   Object Literal is generally used to create a single object. The constructor function is useful if you want to create multiple objects. For example,

    // using object literal
    let person = {
        name: 'Sam'
    }

    // using constructor function
    function Person () {
        this.name = 'Sam'
    }

    let person1 = new Person();
    let person2 = new Person();

*   Each object created from the constructor function is unique. You can have the same properties as the constructor function or add a new property to one particular object. For example,

    // using constructor function
    function Person () {
        this.name = 'Sam'
    }

    let person1 = new Person();
    let person2 = new Person();

    // adding new property to person1
    person1.age = 20;

Now this `age` property is unique to `person1` object and is not available to `person2` object.

However, if an object is created with an object literal, and if a variable is defined with that object value, any changes in variable value will change the original object. For example,

    // using object lateral
    let person = {
        name: 'Sam'
    }

    console.log(person.name); // Sam

    let student = person;

    // changes the property of an object
    student.name = 'John';

    // changes the origins object property
    console.log(person.name); // John

[Run Code](/javascript/online-compiler)

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

When an object is created with an object literal, any object variable derived from that object will act as a clone of the original object. Hence, any change you make in one object will also reflect in the other object.

* * *

Adding Properties And Methods in an Object
------------------------------------------

You can add properties or methods in an object like this:

    // constructor function
    function Person () {
        this.name = 'John',
        this.age = 23
    }

    // creating objects
    let person1 = new Person();
    let person2 = new Person();

    // adding property to person1 object
    person1.gender = 'male';

    // adding method to person1 object
    person1.greet = function () {
        console.log('hello');
    }

    person1.greet();   // hello

    // Error code
    // person2 doesn't have greet() method
    person2.greet();

[Run Code](/javascript/online-compiler)

**Output**

hello
Uncaught TypeError: person2.greet is not a function

In the above example, a new property `gender` and a new method `greet()` is added to the `person1` object.

However, this new property and method is only added to `person1`. You cannot access `gender` or `greet()` from `person2`. Hence the program gives error when we try to access `person2.greet();`

* * *

JavaScript Object Prototype
---------------------------

You can also add properties and methods to a constructor function using a **prototype**. For example,

    // constructor function
    function Person () {
        this.name = 'John',
        this.age = 23
    }

    // creating objects
    let person1 = new Person();
    let person2 = new Person();

    // adding new property to constructor function
    Person.prototype.gender = 'Male';

    console.log(person1.gender); // Male
    console.log(person2.gender); // Male

[Run Code](/javascript/online-compiler)

To learn more about prototypes, visit [JavaScript Prototype](https://www.programiz.com/javascript/prototype).

* * *

JavaScript Built-in Constructors
--------------------------------

JavaScript also has built-in constructors. Some of them are:

    let a = new Object();    // A new Object object
    let b = new String();    // A new String object
    let c = new Number();    // A new Number object
    let d = new Boolean();   // A new Boolean object

In JavaScript, strings can be created as objects by:

    const name = new String ('John');
    console.log(name); // "John"

[Run Code](/javascript/online-compiler)

In JavaScript, numbers can be created as objects by:

    const number = new Number (57);
    console.log(number); // 57

[Run Code](/javascript/online-compiler)

In JavaScript, booleans can be created as objects by:

    const count = new Boolean(true);
    console.log(count); // true

[Run Code](/javascript/online-compiler)

**Note**: It is recommended to use primitive data types and create them in a normal way, such as `const name = 'John';`, `const number = 57;` and `const count = true;`

You should not declare strings, numbers, and boolean values as objects because they slow down the program.

* * *

**Note**: In JavaScript, the keyword `class` was introduced in ES6 (ES2015) that also allows us to create objects. Classes are similar to constructor functions in JavaScript. To learn more, visit [JavaScript Classes](https://www.programiz.com/javascript/ES6#class).
JavaScript Getter and Setter
============================

In this tutorial, you will learn about JavaScript getter and setter methods with the help of examples.

In JavaScript, there are two kinds of object properties:

*   Data properties
*   Accessor properties

* * *

Data Property
-------------

Here's an example of data property that we have been using in the previous tutorials.

    const student = {

        // data property
        firstName: 'Monica';
    };

* * *

Accessor Property
-----------------

In JavaScript, accessor properties are methods that get or set the value of an object. For that, we use these two keywords:

*   `get` - to define a getter method to get the property value
*   `set` - to define a setter method to set the property value

* * *

### JavaScript Getter

In JavaScript, getter methods are used to access the properties of an object. For example,

    const student = {

        // data property
        firstName: 'Monica',

        // accessor property(getter)
        get getName() {
            return this.firstName;
        }
    };

    // accessing data property
    console.log(student.firstName); // Monica

    // accessing getter methods
    console.log(student.getName); // Monica

    // trying to access as a method
    console.log(student.getName()); // error

[Run Code](/javascript/online-compiler)

In the above program, a getter method `getName()` is created to access the property of an object.

    get getName() {
        return this.firstName;
    }

**Note:** To create a getter method, the `get` keyword is used.

And also when accessing the value, we access the value as a property.

    student.getName;

When you try to access the value as a method, an error occurs.

    console.log(student.getName()); // error

* * *

JavaScript Setter
-----------------

In JavaScript, setter methods are used to change the values of an object. For example,

    const student = {
        firstName: 'Monica',

        //accessor property(setter)
        set changeName(newName) {
            this.firstName = newName;
        }
    };

    console.log(student.firstName); // Monica

    // change(set) object property using a setter
    student.changeName = 'Sarah';

    console.log(student.firstName); // Sarah

[Run Code](/javascript/online-compiler)

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

In the above example, the setter method is used to change the value of an object.

    set changeName(newName) {
        this.firstName = newName;
    }

**Note:** To create a setter method, the `set` keyword is used.

As shown in the above program, the value of `firstName` is `Monica`.

Then the value is changed to `Sarah`.

    student.changeName = 'Sarah';

**Note**: Setter must have exactly one formal parameter.

* * *

JavaScript Object.defineProperty()
----------------------------------

In JavaScript, you can also use `Object.defineProperty()` method to add getters and setters. For example,

    const student = {
        firstName: 'Monica'
    }

    // getting property
    Object.defineProperty(student, "getName", {
        get : function () {
            return this.firstName;
        }
    });

    // setting property
    Object.defineProperty(student, "changeName", {
        set : function (value) {
            this.firstName = value;
        }
    });

    console.log(student.firstName); // Monica

    // changing the property value
    student.changeName = 'Sarah';

    console.log(student.firstName); // Sarah

[Run Code](/javascript/online-compiler)

In the above example, `Object.defineProperty()` is used to access and change the property of an object.

The syntax for using `Object.defineProperty()` is:

    Object.defineProperty(obj, prop, descriptor)

The `Object.defineProperty()` method takes three arguments.

*   The first argument is the objectName.
*   The second argument is the name of the property.
*   The third argument is an object that describes the property.

JavaScript Prototype
====================

In this tutorial, you will learn about prototypes in JavaScript with the help of examples.

Before you learn prototypes, be sure to check these tutorials:

*   [JavaScript Objects](https://www.programiz.com/javascript/object)
*   [JavaScript Constructor Function](https://www.programiz.com/javascript/constructor-function)

As you know, you can create an object in JavaScript using an object constructor function. For example,

    // constructor function
    function Person () {
        this.name = 'John',
        this.age = 23
    }

    // creating objects
    const person1 = new Person();
    const person2 = new Person();

[Run Code](/javascript/online-compiler)

In the above example, `function Person()` is an object constructor function. We have created two objects `person1` and `person2` from it.

* * *

JavaScript Prototype
--------------------

In JavaScript, every function and object has a property named prototype by default. For example,

    function Person () {
        this.name = 'John',
        this.age = 23
    }

    const person = new Person();

    // checking the prototype value
    console.log(Person.prototype); // { ... }

[Run Code](/javascript/online-compiler)

In the above example, we are trying to access the prototype property of a `Person` constructor function.

Since the prototype property has no value at the moment, it shows an empty object { ... }.

* * *

Prototype Inheritance
---------------------

In JavaScript, a prototype can be used to add properties and methods to a constructor function. And objects inherit properties and methods from a prototype. For example,

    // constructor function
    function Person () {
        this.name = 'John',
        this.age = 23
    }

    // creating objects
    const person1 = new Person();
    const person2 = new Person();

    // adding property to constructor function
    Person.prototype.gender = 'male';

    // prototype value of Person
    console.log(Person.prototype);

    // inheriting the property from prototype
    console.log(person1.gender);
    console.log(person2.gender);

[Run Code](/javascript/online-compiler)

**Output**

{ gender: "male" }
male
male

In the above program, we have added a new property `gender` to the `Person` constructor function using:

    Person.prototype.gender = 'male';

Then object `person1` and `person2` inherits the property `gender` from the prototype property of `Person` constructor function.

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

Hence, both objects `person1` and `person2` can access the gender property.

**Note:** The syntax to add the property to an object constructor function is:

    objectConstructorName.prototype.key = 'value';

Prototype is used to provide additional property to all the objects created from a constructor function.

* * *

### Add Methods to a Constructor Function Using Prototype

You can also add new methods to a constructor function using prototype. For example,

    // constructor function
    function Person () {
        this.name = 'John',
        this.age = 23
    }

    // creating objects
    const person1 = new Person();
    const person2 = new Person();

    // adding a method to the constructor function
    Person.prototype.greet = function() {
        console.log('hello' + ' ' +  this.name);
    }

    person1.greet(); // hello John
    person2.greet(); // hello John

[Run Code](/javascript/online-compiler)

In the above program, a new method `greet` is added to the `Person` constructor function using a prototype.

* * *

Changing Prototype
------------------

If a prototype value is changed, then all the new objects will have the changed property value. All the previously created objects will have the previous value. For example,

    // constructor function
    function Person() {
        this.name = 'John'
    }

    // add a property
    Person.prototype.age = 20;

    // creating an object
    const person1 = new Person();

    console.log(person1.age); // 20

    // changing the property value of prototype
    Person.prototype = { age: 50 }

    // creating new object
    const person3 = new Person();

    console.log(person3.age); // 50
    console.log(person1.age); // 20

[Run Code](/javascript/online-compiler)

**Note**: You should not modify the prototypes of standard JavaScript built-in objects like strings, arrays, etc. It is considered a bad practice.

* * *

JavaScript Prototype Chaining
-----------------------------

If an object tries to access the same property that is in the constructor function and the prototype object, the object takes the property from the constructor function. For example,

    function Person() {
        this.name = 'John'
    }

    // adding property
    Person.prototype.name = 'Peter';
    Person.prototype.age = 23

    const person1 = new Person();

    console.log(person1.name); // John
    console.log(person1.age); // 23

[Run Code](/javascript/online-compiler)

In the above program, a property name is declared in the constructor function and also in the prototype property of the constructor function.

When the program executes, `person1.name` looks in the constructor function to see if there is a property named `name`. Since the constructor function has the name property with value `'John'`, the object takes value from that property.

When the program executes, `person1.age` looks in the constructor function to see if there is a property named `age`. Since the constructor function doesn't have `age` property, the program looks into the prototype object of the constructor function and the object inherits property from the prototype object (if available).

* * *

**Note**: You can also access the prototype property of a constructor function from an object.

    function Person () {
        this.name = 'John'
    }

    // adding a prototype
    Person.prototype.age = 24;

    // creating object
    const person = new Person();

    // accessing prototype property
    console.log(person.__proto__);   // { age: 24 }

[Run Code](/javascript/online-compiler)

In the above example, a `person` object is used to access the prototype property using `__proto__`. However, `__proto__` has been deprecated and you should avoid using it.

JavaScript Arrays
=================

In this tutorial, you will learn about JavaScript arrays with the help of examples.

An array is an object that can store multiple values at once. For example,

    const words = ['hello', 'world', 'welcome'];

Here, words is an array. The array is storing 3 values.

* * *

Create an Array
---------------

You can create an array using two ways:

**1\. Using an array literal**

The easiest way to create an array is by using an array literal `[]`. For example,

    const array1 = ["eat", "sleep"];

**2.** **Using the new keyword**

You can also create an array using JavaScript's `new` keyword.

    const array2 = new Array("eat", "sleep");

In both of the above examples, we have created an array having two elements.

**Note**: It is recommended to use array literal to create an array.

Here are more examples of arrays:

    // empty array
    const myList = [ ];

    // array of numbers
    const numberArray = [ 2, 4, 6, 8];

    // array of strings
    const stringArray = [ 'eat', 'work', 'sleep'];

    // array with mixed data types
    const newData = ['work', 'exercise', 1, true];

You can also store arrays, functions and other objects inside an array. For example,

    const newData = [
        {'task1': 'exercise'},
        [1, 2 ,3],
        function hello() { console.log('hello')}
    ];

* * *

Access Elements of an Array
---------------------------

You can access elements of an array using indices **(0, 1, 2 …)**. For example,

    const myArray = ['h', 'e', 'l', 'l', 'o'];

    // first element
    console.log(myArray[0]);  // "h"

    // second element
    console.log(myArray[1]); // "e"

[Run Code](/javascript/online-compiler)

![Array indexing in JavaScript](//cdn.programiz.com/sites/tutorial2program/files/javascript-array-indexing.png "Array indexing in JavaScript")

Array indexing in JavaScript

**Note**: Array's index starts with 0, not 1.

* * *

Add an Element to an Array
--------------------------

You can use the built-in method `push()` and `unshift()` to add elements to an array.

The `push()` method adds an element at the end of the array. For example,

    let dailyActivities = ['eat', 'sleep'];

    // add an element at the end
    dailyActivities.push('exercise');

    console.log(dailyActivities); //  ['eat', 'sleep', 'exercise']

[Run Code](/javascript/online-compiler)

The `unshift()` method adds an element at the beginning of the array. For example,

    let dailyActivities = ['eat', 'sleep'];

    //add an element at the start
    dailyActivities.unshift('work');

    console.log(dailyActivities); // ['work', 'eat', 'sleep']

[Run Code](/javascript/online-compiler)

* * *

Change the Elements of an Array
-------------------------------

You can also add elements or change the elements by accessing the index value.

    let dailyActivities = [ 'eat', 'sleep'];

    // this will add the new element 'exercise' at the 2 index
    dailyActivities[2] = 'exercise';

    console.log(dailyActivities); // ['eat', 'sleep', 'exercise']

[Run Code](/javascript/online-compiler)

Suppose, an array has two elements. If you try to add an element at index 3 (fourth element), the third element will be undefined. For example,

    let dailyActivities = [ 'eat', 'sleep'];

    // this will add the new element 'exercise' at the 3 index
    dailyActivities[3] = 'exercise';

    console.log(dailyActivities); // ["eat", "sleep", undefined, "exercise"]

[Run Code](/javascript/online-compiler)

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

Basically, if you try to add elements to high indices, the indices in between will have undefined value.

* * *

Remove an Element from an Array
-------------------------------

You can use the `pop()` method to remove the last element from an array. The `pop()` method also returns the returned value. For example,

    let dailyActivities = ['work', 'eat', 'sleep', 'exercise'];

    // remove the last element
    dailyActivities.pop();
    console.log(dailyActivities); // ['work', 'eat', 'sleep']

    // remove the last element from ['work', 'eat', 'sleep']
    const removedElement = dailyActivities.pop();

    //get removed element
    console.log(removedElement); // 'sleep'
    console.log(dailyActivities);  // ['work', 'eat']

[Run Code](/javascript/online-compiler)

If you need to remove the first element, you can use the `shift()` method. The `shift()` method removes the first element and also returns the removed element. For example,

    let dailyActivities = ['work', 'eat', 'sleep'];

    // remove the first element
    dailyActivities.shift();

    console.log(dailyActivities); // ['eat', 'sleep']

[Run Code](/javascript/online-compiler)

* * *

Array length
------------

You can find the length of an element (the number of elements in an array) using the `length` property. For example,

    const dailyActivities = [ 'eat', 'sleep'];

    // this gives the total number of elements in an array
    console.log(dailyActivities.length); // 2

* * *

Array Methods
-------------

In JavaScript, there are various array methods available that makes it easier to perform useful calculations.

Some of the commonly used JavaScript array methods are:

Method

Description

concat()

joins two or more arrays and returns a result

indexOf()

searches an element of an array and returns its position

find()

returns the first value of an array element that passes a test

findIndex()

returns the first index of an array element that passes a test

forEach()

calls a function for each element

includes()

checks if an array contains a specified element

push()

aads a new element to the end of an array and returns the new length of an array

unshift()

adds a new element to the beginning of an array and returns the new length of an array

pop()

removes the last element of an array and returns the removed element

shift()

removes the first element of an array and returns the removed element

sort()

sorts the elements alphabetically in strings and in ascending order

slice()

selects the part of an array and returns the new array

splice()

removes or replaces existing elements and/or adds new elements

### Example: JavaScript Array Methods

    let dailyActivities = ['sleep', 'work', 'exercise']
    let newRoutine = ['eat'];

    // sorting elements in the alphabetical order
    dailyActivities.sort();
    console.log(dailyActivities); // ['exercise', 'sleep', 'work']

    //finding the index position of string
    const position = dailyActivities.indexOf('work');
    console.log(position); // 2

    // slicing the array elements
    const newDailyActivities = dailyActivities.slice(1);
    console.log(newDailyActivities); // [ 'sleep', 'work']

    // concatenating two arrays
    const routine = dailyActivities.concat(newRoutine);
    console.log(routine); // ["exercise", "sleep", "work", "eat"]

[Run Code](/javascript/online-compiler)

**Note**: If the element is not in an array, `indexOf()` gives -1.

Visit [JavaScript Array Methods](https://www.programiz.com/javascript/library/array) to learn more.

* * *

Working of JavaScript Arrays
----------------------------

In JavaScript, an array is an object. And, the indices of arrays are objects keys.

Since arrays are objects, the array elements are stored by reference. Hence, when an array value is copied, any change in the copied array will also reflect in the original array. For example,

    let arr = ['h', 'e'];
    let arr1 = arr;
    arr1.push('l');

    console.log(arr); // ["h", "e", "l"]
    console.log(arr1); // ["h", "e", "l"]

[Run Code](/javascript/online-compiler)

You can also store values by passing a named key in an array. For example,

    let arr = ['h', 'e'];
    arr.name = 'John';

    console.log(arr); // ["h", "e"]
    console.log(arr.name); // "John"
    console.log(arr['name']); // "John"

[Run Code](/javascript/online-compiler)

![Array indexing in JavaScript](//cdn.programiz.com/cdn/farfuture/1boQBEa6BRhsaADEL93Czau6ABhpoHq4t3735VgO1O8/mtime:1594110571/sites/tutorial2program/files/array-indexing1.png "Array indexing in JavaScript")

Array indexing in JavaScript

However, it is not recommended to store values by passing arbitrary names in an array.

Hence in JavaScript, you should use an array if values are in ordered collection. Otherwise it's better to use object with `{ }`.

* * *

**Recommended Articles**

*   [JavaScript forEach](https://www.programiz.com/javascript/forEach)
*   [JavaScript for...of](https://www.programiz.com/javascript/for-of)
*   [JavaScript Multidimensional Array](https://www.programiz.com/javascript/multidimensional-array)

JavaScript Multidimensional Array
=================================

In this tutorial, you will learn about JavaScript multidimensional arrays with the help of examples.

A multidimensional array is an [array](/javascript/array) that contains another array. For example,

    // multidimensional array
    const data = [[1, 2, 3], [1, 3, 4], [4, 5, 6]];

* * *

Create a Multidimensional Array
-------------------------------

Here is how you can create multidimensional arrays in JavaScript.

**Example 1**

    let studentsData = [['Jack', 24], ['Sara', 23], ['Peter', 24]];

**Example 2**

    let student1 = ['Jack', 24];
    let student2 = ['Sara', 23];
    let student3 = ['Peter', 24];

    // multidimensional array
    let studentsData = [student1, student2, student3];

Here, both example 1 and example 2 creates a multidimensional array with the same data.

* * *

Access Elements of an Array
---------------------------

You can access the elements of a multidimensional array using indices **(0, 1, 2 …)**. For example,

    let x = [
    ['Jack', 24],
    ['Sara', 23],
    ['Peter', 24]
    ];

    // access the first item
    console.log(x[0]); // ["Jack", 24]

    // access the first item of the first inner array
    console.log(x[0][0]); // Jack

    // access the second item of the third inner array
    console.log(x[2][1]); // 24

[Run Code](/javascript/online-compiler)

You can think of a multidimensional array (in this case, x), as a table with 3 rows and 2 columns.

![Accessing multidimensional array elements](//cdn.programiz.com/sites/tutorial2program/files/multidimensional-array.png "Accessing multidimensional array elements")

Accessing multidimensional array elements

* * *

Add an Element to a Multidimensional Array
------------------------------------------

You can use the [Array's push()](/javascript/library/array/push) [met](/javascript/library/array/push)[hod](/javascript/library/array/push) or an indexing notation to add elements to a multidimensional array.

**Adding Element to the Outer Array**

    let studentsData = [['Jack', 24], ['Sara', 23],];
    studentsData.push(['Peter', 24]);

    console.log(studentsData); //[["Jack", 24], ["Sara", 23], ["Peter", 24]

[Run Code](/javascript/online-compiler)

**Adding Element to the Inner Array**

    // using index notation
    let studentsData = [['Jack', 24], ['Sara', 23],];
    studentsData[1][2] = 'hello';

    console.log(studentsData); // [["Jack", 24], ["Sara", 23, "hello"]]

[Run Code](/javascript/online-compiler)

    // using push()
    let studentsData = [['Jack', 24], ['Sara', 23],];
    studentsData[1].push('hello');

    console.log(studentsData); // [["Jack", 24], ["Sara", 23, "hello"]]

[Run Code](/javascript/online-compiler)

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

You can also use the [Array's](/javascript/library/array/splice) [splice() m](/javascript/library/array/splice)[ethod](/javascript/library/array/splice) to add an element at a specified index. For example,

    let studentsData = [['Jack', 24], ['Sara', 23],];

    // adding element at 1 index
    studentsData.splice(1, 0, ['Peter', 24]);

    console.log(studentsData); // [["Jack", 24], ["Peter", 24], ["Sara", 23]]

[Run Code](/javascript/online-compiler)

* * *

Remove an Element from a Multidimensional Array
-----------------------------------------------

You can use the [Array's](/javascript/library/array/pop) [pop() met](/javascript/library/array/pop)[hod](/javascript/library/array/pop) to remove the element from a multidimensional array. For example,

**Remove Element from Outer Array**

    // remove the array element from outer array
    let studentsData = [['Jack', 24], ['Sara', 23],];
    studentsData.pop();

    console.log(studentsData); // [["Jack", 24]]

[Run Code](/javascript/online-compiler)

**Remove Element from Inner Array**

    // remove the element from the inner array
    let studentsData = [['Jack', 24], ['Sara', 23]];
    studentsData[1].pop();

    console.log(studentsData); // [["Jack", 24], ["Sara"]]

[Run Code](/javascript/online-compiler)

You can also use the `splice()` method to remove an element at a specified index. For example,

    let studentsData = [['Jack', 24], ['Sara', 23],];

    // removing 1 index array item
    studentsData.splice(1,1);
    console.log(studentsData); // [["Jack", 24]]

[Run Code](/javascript/online-compiler)

* * *

Iterating over Multidimensional Array
-------------------------------------

You can iterate over a multidimensional array using the [Array's forEach() method](/javascript/library/array/foreach) to iterate over the multidimensional array. For example,

    let studentsData = [['Jack', 24], ['Sara', 23],];

    // iterating over the studentsData
    studentsData.forEach((student) => {
        student.forEach((data) => {
            console.log(data);
        });
    });

[Run Code](/javascript/online-compiler)

**Output**

Jack
24
Sara
23

The first `forEach()` method is used to iterate over the outer array elements and the second `forEach()` is used to iterate over the inner array elements.

You can also use the `for...of` loop to iterate over the multidimensional array. For example,

    let studentsData = [['Jack', 24], ['Sara', 23],];

    for (let i of studentsData) {
      for (let j of i) {
        console.log(j);
      }
    }

[Run Code](/javascript/online-compiler)

You can also use the [for loop](/javascript/for-loop) to iterate over a multidimensional array. For example,

    let studentsData = [['Jack', 24], ['Sara', 23],];

    // looping outer array elements
    for(let i = 0; i < studentsData.length; i++){

        // get the length of the inner array elements
        let innerArrayLength = studentsData[i].length;

        // looping inner array elements
        for(let j = 0; j < innerArrayLength; j++) {
            console.log(studentsData[i][j]);
        }
    }

[Run Code](/javascript/online-compiler)

JavaScript String
=================

In this tutorial, you will learn about JavaScript string with the help of examples.

JavaScript string is a primitive data type that is used to work with texts. For example,

    const name = 'John';

* * *

Create JavaScript Strings
-------------------------

In JavaScript, strings are created by surrounding them with quotes. There are three ways you can use quotes.

*   **Single quotes:** `'Hello'`
*   **Double quotes:** `"Hello"`
*   **Backticks:** `` `Hello` ``

For example,

    //strings example
    const name = 'Peter';
    const name1 = "Jack";
    const result = `The names are ${name} and ${name1}`;

Single quotes and double quotes are practically the same and you can use either of them.

Backticks are generally used when you need to include variables or expressions into a string. This is done by wrapping variables or expressions with `${variable or expression}` as shown above.

You can also write a quote inside another quote. For example,

    const name = 'My name is "Peter".';

However, the quote should not match the surrounding quotes. For example,

    const name = 'My name is 'Peter'.'; // error

* * *

Access String Characters
------------------------

You can access the characters in a string in two ways.

*   One way is to treat strings as an array. For example,

    const a = 'hello';
    console.log(a[1]); // "e"

*   Another way is to use the method `charAt()`. For example,

    const a = 'hello';
    console.log(a.charAt(1)); // "e"

* * *

JavaScript Strings are immutable
--------------------------------

In JavaScript, strings are immutable. That means the characters of a string cannot be changed. For example,

    let a = 'hello';
    a[0] = 'H';
    console.log(a); // "hello"

However, you can assign the variable name to a new string. For example,

    let a = 'hello';
    a = 'Hello';
    console.log(a); // "Hello"

* * *

JavaScript is Case-Sensitive
----------------------------

JavaScript is case-sensitive. That means in JavaScript, the lowercase and uppercase letters are treated as different values. For example,

    const a = 'a';
    const b = 'A'
    console.log(a === b); // false

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

In JavaScript, `a` and `A` are treated as different values.

* * *

JavaScript Multiline Strings
----------------------------

To use a multiline string, you can either use the `+` operator or the `\` operator. For example,

    // using the + operator
    const message1 = 'This is a long message ' +
        'that spans across multiple lines' +
        'in the code.'

    // using the \ operator
    const message2 = 'This is a long message \
    that spans across multiple lines \
    in the code.'

* * *

JavaScript String Length
------------------------

To find the length of a string, you can use built-in `length` property. For example,

    const a = 'hello';
    console.log(a.length); // 5

* * *

JavaScript String Objects
-------------------------

You can also create strings using the `new` keyword. For example,

    const a = 'hello';
    const b = new String('hello');

    console.log(a); // "hello"
    console.log(b); // "hello"

    console.log(typeof a); // "string"
    console.log(typeof b); // "object"

[Run Code](/javascript/online-compiler)

**Note**: It is recommended to avoid using string objects. Using string objects slows down the program.

* * *

JavaScript String Methods
-------------------------

Here are the commonly used JavaScript String methods:

Method

Description

charAt(index)

returns the character at the specified index

concat()

joins two or more strings

replace()

replaces a string with another string

split()

converts the string to an array of strings

substr(start, length)

returns a part of a string

substring(start,end)

returns a part of a string

slice(start, end)

returns a part of a string

toLowerCase()

returns the passed string in lower case

toUpperCase()

returns the passed string in upper case

trim()

removes whitespace from the strings

includes()

searches for a string and returns a boolean value

search()

searches for a string and returns a position of a match

### Example: JavaScript String Methods

    const text1 = 'hello';
    const text2 = 'world';
    const text3 = '     JavaScript    ';

    // concatenating two strings
    const result1 = text1.concat(' ', text2);
    console.log(result1); // "hello world"

    // converting the text to uppercase
    const result2 = text1.toUpperCase();
    console.log(result2); // HELLO

    // removing whitespace from the string
    const result3 = text3.trim();
    console.log(result3); // JavaScript

    // converting the string to an array
    const result4 = text1.split();
    console.log(result4); // ["hello"]

    // slicing the string
    const result5= text1.slice(1, 3);
    console.log(result5); // "el"

[Run Code](/javascript/online-compiler)

* * *

JavaScript String() Function
----------------------------


The `String()` function is used to convert various data types to strings. For example,

    const a = 225; // number
    const b = true; // boolean

    //converting to string
    const result1 = String(a);
    const result2 = String(b);

    console.log(result1); // "225"
    console.log(result2); // "true"

[Run Code](/javascript/online-compiler)

If you want to learn more about the string conversion, visit [JavaScript Type Conversion](/javascript/type-conversion).

* * *

Escape Character
----------------

You can use the backslash escape character `\` to include special characters in a string. For example,

    const name = 'My name is \'Peter\'.';
    console.log(name);

[Run Code](/javascript/online-compiler)

**Output**

My name is 'Peter'.

In the above program, the same quote is included using `\`.

Here are other ways that you can use `\`:

Code

Output

\\"

include double quote

\\\\

include backslash

\\n

new line

\\r

carriage return

\\v

vertical tab

\\t

horizontal tab

\\b

backspace

\\f

form feed

JavaScript for...in loop
========================

In this tutorial, you will learn about the JavaScript for...in loop with the help of examples.

In the previous tutorials, we have covered:

*   [JavaScript while and do...while loop](/javascript/while-loop)
*   [JavaScript for loop](/javascript/for-loop)

There are also other types of loops. The `for..in` loop in JavaScript allows you to iterate over all property keys of an object.

* * *

JavaScript for...in loop
------------------------

The syntax of the `for...in` loop is:

    for (key in object) {
        // body of for...in
    }

In each iteration of the loop, a key is assigned to the key variable. The loop continues for all object properties.

**Note**: Once you get keys, you can easily find their corresponding values.

* * *

### Example 1: Iterate Through an Object

    const student = {
        name: 'Monica',
        class: 7,
        age: 12
    }

    // using for...in
    for ( let key in student ) {

        // display the properties
        console.log(`${key} => ${student[key]}`);
    }

[Run Code](/javascript/online-compiler)

**Output**

name => Monica
class => 7
age => 12

In the above program, the `for...in` loop is used to iterate over the `student` object and print all its properties.

*   The object key is assigned to the variable key.
*   `student[key]` is used to access the value of key.

* * *

### Example 2: Update Values of Properties

    const salaries= {
        Jack : 24000,
        Paul : 34000,
        Monica : 55000
    }

    // using for...in
    for ( let i in salaries) {

        // add a currency symbol
        let salary = "$" + salaries[i];

        // display the values
        console.log(`${i} : ${salary}`);
    }

[Run Code](/javascript/online-compiler)

**Output**

Jack : $24000,
Paul : $34000,
Monica : $55000

In the above example, the `for...in` loop is used to iterate over the properties of the `salaries` object. Then, the string `$` is added to each value of the object.

* * *

for...in with Strings
---------------------

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

You can also use `for...in` loop to iterate over string values. For example,

    const string = 'code';

    // using for...in loop
    for (let i in string) {
        console.log(string[i]);
    }

[Run Code](/javascript/online-compiler)

**Output**

c
o
d
e

* * *

for...in with Arrays
--------------------

You can also use `for...in` with arrays. For example,

    // define array
    const arr = [ 'hello', 1, 'JavaScript' ];

    // using for...in loop
    for (let x in arr) {
        console.log(arr[x]);
    }

[Run Code](/javascript/online-compiler)

**Output**

hello
1
JavaScript

You will learn more about the arrays in later tutorials.

**Note**: You should not use `for...in` to iterate over an array where the index order is important.

One of the better ways to iterate over an array is using the `for...of` loop.

To learn more about the `for...of` loop, visit [JavaScript for...of loop](https://www.programiz.com/javascript/for-of).

JavaScript Number
=================

In this tutorial, you will learn about JavaScript Number with the help of examples.

In JavaScript, numbers are primitive data types. For example,

    const a = 3;
    const b = 3.13;

Unlike in some other programming languages, you don't have to specifically declare for integer or floating values using **int**, **float**, etc.

You can use exponential notation **e** to include too large or too small numbers. For example,

    const a1 = 5e9;
    console.log(a1); //5000000000

    const a2 = 5e-5;
    console.log(a2); // 0.00005

Numbers can also be denoted in hexadecimal notation. For example,

    const a = 0xff;
    console.log(a); // 255

    const b = 0x00 ;
    console.log(b); // 0

* * *

\+ Operator with Numbers
------------------------

When `+` is used with numbers, it is used to add the numbers. For example,

    const a = 4 + 9;
    console.log(a); // 13

When `+` is used with numbers and strings, it is used to concatenate them. For example,

    const a = '4' + 9;
    console.log(a); // 49

When a numeric string is used with other numeric operations, the numeric string is converted to a number. For example,

    const a = '4' - 2;
    console.log(a); // 2

    const a = '4' / 2;
    console.log(a); // 2

    const a = '4' * 2;
    console.log(a); // 8

* * *

JavaScript NaN
--------------

In JavaScript, `NaN`(Not a Number) is a keyword that indicates that the value is not a number.

Performing arithmetic operations (except `+` ) to numeric value with string results in `NaN`. For example,

    const a = 4 - 'hello';
    console.log(a); // NaN

The built-in function `isNaN()` can be used to find if a value is a number. For example,

    const a = isNaN(9);
    console.log(a); // false

    const a = isNaN(4 - 'hello');
    console.log(a); // true

When the `typeof` operator is used for `NaN` value, it gives a number output. For example,

    const a = 4 - 'hello';
    console.log(a); // NaN
    console.log(typeof a); // "number"

* * *

JavaScript Infinity
-------------------

In JavaScript, when calculation is done that exceeds the largest (or smallest) possible number, `Infinity` (or `-Infinity`) is returned. For example,

    const a = 2 / 0;
    console.log(a); // Infinity

    const a = -2 / 0;
    console.log(a); // -Infinity

* * *

JavaScript BigInt
-----------------

In JavaScript, Number type can only represent numbers less than **(253** **\- 1)** and more than **\-(253** **\- 1)**. However, if you need to use a larger number than that, you can use the BigInt data type.

A BigInt number is created by appending **n** to the end of an integer. For example,

    // BigInt value
    const value = 900719925124740998n;

    // Adding two big integers
    const value1 = value + 1n;
    console.log(value1); // returns "900719925124740999n"

**Note:** BigInt was introduced in the newer version of JavaScript and is not supported by many browsers. Visit [JavaScript BigInt support](https://caniuse.com/#feat=bigint) to learn more.

* * *

JavaScript Numbers Are Stored in 64-bit
---------------------------------------

In JavaScript, numbers are stored in 64-bit format [IEEE-754](https://en.wikipedia.org/wiki/IEEE_754-2008_revision), also known as "double precision floating point numbers".

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

The numbers are stored in 64 bits (the number is stored in 0 to 51 bit positions, the exponent in 52 to 62 bit positions and the sign in 63 bit position).

Numbers

Exponent

Sign

52 bits(0 - 51)

11 bits(52- 62)

1 bit(63)

* * *

Precision Problems
------------------

Operations on floating-point numbers results in some unexpected results. For example,

    const a = 0.1 + 0.2;
    console.log(a); // 0.30000000000000004

[Run Code](/javascript/online-compiler)

The result should be **0.3** instead of **0.30000000000000004**. This error occurs because in JavaScript, numbers are stored in binary form to represent decimal digits internally. And decimal numbers can't be represented in binary form exactly.

To solve the above problem, you can do something like this:

    const a = (0.1 * 10 + 0.2 * 10) / 10;
    console.log(a); // 0.3

You can also use the `toFixed()` method.

    const a = 0.1 + 0.2;
    console.log(a.toFixed(2)); // 0.30

`toFixed(2)` rounds up the decimal number to two decimal values.

    const a = 9999999999999999
    console.log(a); // 10000000000000000

**Note**: Integers are accurate up to 15 digits.

* * *

Number Objects
--------------

You can also create numbers using the `new` keyword. For example,

    const a = 45;

    // creating a number object
    const b = new Number(45);

    console.log(a); // 45
    console.log(b); // 45

    console.log(typeof a); // "number"
    console.log(typeof b); // "object"

[Run Code](/javascript/online-compiler)

**Note**: It is recommended to avoid using number objects. Using number objects slows down the program.

* * *

JavaScript Number Methods
-------------------------

Here is a list of built-in number methods in JavaScript.

Method

Description

isNaN()

determines whether the passed value is NaN

isFinite()

determines whether the passed value is a finite number

isInteger()

determines whether the passed value is an integer

isSafeInteger()

determines whether the passed value is a safe integer

parseFloat(string)

converts the numeric floating string to floating-point number

parseInt(string, \[radix\])

converts the numeric string to integer

toExponential(fractionDigits)

returns a string value for a number in exponential notation

toFixed(digits)

returns a string value for a number in fixed-point notation

toPrecision()

returns a string value for a number to a specified precision

toString(\[radix\])

returns a string value in a specified radix(base)

valueof()

returns the numbers value

toLocaleString()

returns a string with a language sensitive representation of a number

For example,

    // check if a is integer
    const a = 12;
    console.log(Number.isInteger(a)); // true

    // check if b is NaN
    const b = NaN;
    console.log(Number.isNaN(b)); // true

    // display upto two decimal point
    const d = 5.1234;
    console.log(d.toFixed(2)); // 5.12

[Run Code](/javascript/online-compiler)

* * *

JavaScript Number Properties
----------------------------

Here is a list of Number properties in JavaScript.

Property

Description

EPSILON

returns the smallest interval between two representable numbers

MAX\_SAFE\_INTEGER

returns the maximum safe integer

MAX\_VALUE

returns the largest possible value

MIN\_SAFE\_INTEGER

returns the minimum safe integer

MIN\_VALUE

returns the smallest possible value

NaN

represents 'Not-a-Number' value

NEGATIVE\_INFINITY

represents negative infinity

POSITIVE\_INFINITY

represents positive infinity

prototype

allows the addition of properties to Number objects

For example,

    // largest possible value
    const a = Number.MAX_VALUE;
    console.log(a); // 1.7976931348623157e+308

    // maximum safe integer
    const a = Number.MAX_SAFE_INTEGER;
    console.log(a); // 9007199254740991

[Run Code](/javascript/online-compiler)

* * *

JavaScript Number() Function
----------------------------

The `Number()` function is used to convert various data types to numbers. For example,

    const a = '23'; // string
    const b = true; // boolean

    //converting to number
    const result1 = Number(a);
    const result2 = Number(b);

    console.log(result1); // 23
    console.log(result2); // 1

[Run Code](/javascript/online-compiler)

If you want to learn more about the number conversion, visit [JavaScript Type Conversion](/javascript/type-conversion).

JavaScript Symbol
=================

In this tutorial, you will learn about JavaScript Symbol with the help of examples.

JavaScript Symbol
-----------------

The JavaScript **ES6** introduced a new primitive data type called `Symbol`. Symbols are immutable (cannot be changed) and are unique. For example,

    // two symbols with the same description

    const value1 = Symbol('hello');
    const value2 = Symbol('hello');

    console.log(value1 === value2); // false

Though value1 and value2 both contain the same description, they are different.

* * *

Creating Symbol
---------------

You use the `Symbol()` function to create a `Symbol`. For example,

    // creating symbol
    const x = Symbol()

    typeof x; // symbol

You can pass an optional string as its description. For example,

    const x = Symbol('hey');
    console.log(x); // Symbol(hey)

* * *

Access Symbol Description
-------------------------

To access the description of a symbol, we use the `.` operator. For example,

    const x = Symbol('hey');
    console.log(x.description); // hey

* * *

Add Symbol as an Object Key
---------------------------

You can add symbols as a **key** in an object using square brackets `[]`. For example,

    let id = Symbol("id");

    let person = {
        name: "Jack",

        // adding symbol as a key
        [id]: 123 // not "id": 123
    };

    console.log(person); // {name: "Jack", Symbol(id): 123}

* * *

Symbols are not included in for...in Loop
-----------------------------------------

The `for...in` loop does not iterate over Symbolic properties. For example,

    let id = Symbol("id");

    let person = {
        name: "Jack",
        age: 25,
        [id]: 12
    };

    // using for...in
    for (let key in person) {
        console.log(key);
    }

**Output**

name
age

* * *

Benefit of Using Symbols in Object
----------------------------------

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

If the same code snippet is used in various programs, then it is better to use `Symbols` in the object key. It's because you can use the same key name in different codes and avoid duplication issues. For example,

    let person = {
        name: "Jack"
    };

    // creating Symbol
    let id = Symbol("id");

    // adding symbol as a key
    person[id] = 12;

In the above program, if the `person` object is also used by another program, then you wouldn't want to add a property that can be accessed or changed by another program. Hence by using `Symbol`, you create a unique property that you can use.

Now, if the other program also needs to use a property named **id**, just add a Symbol named `id` and there won't be duplication issues. For example,

    let person = {
        name: "Jack"
    };

    let id = Symbol("id");

    person[id] = "Another value";

In the above program, even if the same name is used to store values, the `Symbol` data type will have a unique value.

In the above program, if the string key was used, then the later program would have changed the value of the property. For example,

    let person = {
        name: "Jack"
    };

    // using string as key
    person.id = 12;
    console.log(person.id); // 12

    // Another program overwrites value
    person.id = 'Another value';
    console.log(person.id); // Another value

In the above program, the second `user.id` overwrites the previous value.

* * *

Symbol Methods
--------------

There are various methods available with Symbol.

Method

Description

`for()`

Searches for existing symbols

`keyFor()`

Returns a shared symbol key from the global symbol registry.

`toSource()`

Returns a string containing the source of the Symbol object

`toString()`

Returns a string containing the description of the Symbol

`valueOf()`

Returns the primitive value of the Symbol object.

* * *

### Example: Symbol Methods

    // get symbol by name
    let sym = Symbol.for('hello');
    let sym1 = Symbol.for('id');

    // get name by symbol
    console.log( Symbol.keyFor(sym) ); // hello
    console.log( Symbol.keyFor(sym1) ); // id

* * *

Symbol Properties
-----------------

Properties

Description

`asyncIterator`

Returns the default AsyncIterator for an object

`hasInstance`

Determines if a constructor object recognizes an object as its instance

`isConcatSpreadable`

Indicates if an object should be flattened to its array elements

`iterator`

Returns the default iterator for an object

`match`

Matches against a string

`matchAll`

Returns an iterator that yields matches of the regular expression against a string

`replace`

Replaces matched substrings of a string

`search`

Returns the index within a string that matches the regular expression

`split`

Splits a string at the indices that match a regular expression

`species`

Creates derived objects

`toPrimitive`

Converts an object to a primitive value

`toStringTag`

Gives the default description of an object

`description`

Returns a string containing the description of the symbol

* * *

### Example: Symbol Properties Example

    const x = Symbol('hey');

    // description property
    console.log(x.description); // hey

    const stringArray = ['a', 'b', 'c'];
    const numberArray = [1, 2, 3];

    // isConcatSpreadable property
    numberArray[Symbol.isConcatSpreadable] = false;

    let result = stringArray.concat(numberArray);
    console.log(result); // ["a", "b", "c", [1, 2, 3]]

JavaScript try...catch...finally Statement
==========================================

In this tutorial, you will learn about the try...catch...finally statements to handle exceptions in JavaScript with the help of examples.

The `try`, `catch` and `finally` blocks are used to handle exceptions (a type of an error). Before you learn about them, you need to know about the types of errors in programming.

Types of Errors
---------------

In programming, there can be two types of errors in the code:

**Syntax Error**: Error in the syntax. For example, if you write `consol.log('your result');`, the above program throws a syntax error. The spelling of `console` is a mistake in the above code.

**Runtime Error**: This type of error occurs during the execution of the program. For example,
calling an invalid function or a variable.


These errors that occur during runtime are called **exceptions**. Now, let's see how you can handle these exceptions.

* * *

JavaScript try...catch Statement
--------------------------------

The `try...catch` statement is used to handle the exceptions. Its syntax is:

    try {
        // body of try
    }
    catch(error) {
        // body of catch
    }

The main code is inside the `try` block. While executing the `try` block, if any error occurs, it goes to the `catch` block. The `catch` block handles the errors as per the catch statements.

If no error occurs, the code inside the `try` block is executed and the `catch` block is skipped.

* * *

### Example 1: Display Undeclared Variable

    // program to show try...catch in a program

    const numerator= 100, denominator = 'a';

    try {
         console.log(numerator/denominator);

        // forgot to define variable a
        console.log(a);
    }
    catch(error) {
        console.log('An error caught');
        console.log('Error message: ' + error);
    }

[Run Code](/javascript/online-compiler)

**Output**

NaN
An error caught
Error message: ReferenceError: a is not defined

In the above program, a variable is not defined. When you try to print the a variable, the program throws an error. That error is caught in the `catch` block.

* * *

JavaScript try...catch...finally Statement
------------------------------------------

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

You can also use the `try...catch...finally` statement to handle exceptions. The `finally` block executes both when the code runs successfully or if an error occurs.

The syntax of `try...catch...finally` block is:

    try {
        // try_statements
    }
    catch(error) {
        // catch_statements
    }
    finally() {
        // codes that gets executed anyway
    }

* * *

### Example 2: try...catch...finally Example

    const numerator= 100, denominator = 'a';

    try {
         console.log(numerator/denominator);
         console.log(a);
    }
    catch(error) {
        console.log('An error caught');
        console.log('Error message: ' + error);
    }
    finally {
         console.log('Finally will execute every time');
    }

[Run Code](/javascript/online-compiler)

**Output**

NaN
An error caught
Error message: ReferenceError: a is not defined
Finally will execute every time

In the above program, an error occurs and that error is caught by the `catch` block. The `finally` block will execute in any situation ( if the program runs successfully or if an error occurs).

**Note**: You need to use `catch` or `finally` statement after `try` statement. Otherwise, the program will throw an error Uncaught SyntaxError: Missing catch or finally after try.

* * *

JavaScript try...catch in setTimeout
------------------------------------

The `try...catch` won't catch the exception if it happened in "**timed**" code, like in [setTimeout()](/javascript/setTimeout). For example,

    try {
        setTimeout(function() {
            // error in the code
        }, 3000);
    } catch (e) {
      console.log( "won't work" );
    }

The above `try...catch` won't work because the engine has already left the `try..catch` construct and the function is executed later.

The `try..catch` block must be inside that function to catch an exception inside a timed function. For example,

    setTimeout(function() {
        try {
            // error in the code
        } catch {
            console.log( "error is caught" );
        }
    }, 3000);

* * *

You can also use the `throw` statement with the `try...catch` statement to use user-defined exceptions. For example, a certain number is divided by **0**. If you want to consider `Infinity` as an error in the program, then you can throw a user-defined exception using the `throw` statement to handle that condition.

You will learn about the [JavaScript throw Statement](/javascript/throw) in the next tutorial.
JavaScript throw Statement
==========================

In this tutorial, you will learn about JavaScript throw statements with the help of examples.

In the previous tutorial, you learned to handle exceptions using [JavaScript try..catch statement](/javascript/try-catch-finally). The try and catch statements handle exceptions in a standard way which is provided by JavaScript. However, you can use the `throw` statement to pass user-defined exceptions.

In JavaScript, the `throw` statement handles user-defined exceptions. For example, if a certain number is divided by **0**, and if you need to consider `Infinity` as an exception, you can use the `throw` statement to handle that exception.

* * *

JavaScript throw statement
--------------------------

The syntax of throw statement is:

    throw expression;

Here, `expression` specifies the value of the exception.

For example,

    const number = 5;
    throw number/0; // generate an exception when divided by 0

**Note**: The expression can be string, boolean, number, or object value.

* * *

JavaScript throw with try...catch
---------------------------------

The syntax of `try...catch...throw` is:

    try {
        // body of try
        throw exception;
    }
    catch(error) {
        // body of catch
    }

**Note**: When the throw statement is executed, it exits out of the block and goes to the `catch` block. And the code below the `throw` statement is not executed.

* * *

### Example 1: try...catch...throw Example

    const number = 40;
    try {
        if(number > 50) {
            console.log('Success');
        }
        else {

            // user-defined throw statement
            throw new Error('The number is low');
        }

        // if throw executes, the below code does not execute
        console.log('hello');
    }
    catch(error) {
        console.log('An error caught');
        console.log('Error message: ' + error);
    }

[Run Code](/javascript/online-compiler)

**Output**

An error caught
Error message: Error: The number is low

In the above program, a condition is checked. If the number is less than **51**, an error is thrown. And that error is thrown using the `throw` statement.

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

The `throw` statement specifies the string `The number is low` as an expression.

**Note**: You can also use other built-in error constructors for standard errors: `TypeError`, `SyntaxError`, `ReferenceError`, `EvalError`, `InternalError`, and `RangeError`.

For example,

    throw new ReferenceError('this is reference error');

* * *

Rethrow an Exception
--------------------

You can also use `throw` statement inside the `catch` block to rethrow an exception. For example,

    const number = 5;
    try {
         // user-defined throw statement
         throw new Error('This is the throw');

    }
    catch(error) {
        console.log('An error caught');
        if( number + 8 > 10) {

            // statements to handle exceptions
             console.log('Error message: ' + error);
            console.log('Error resolved');
        }
        else {
            // cannot handle the exception
            // rethrow the exception
            throw new Error('The value is low');
        }
    }

[Run Code](/javascript/online-compiler)

**Output**

An error caught
Error message: Error: This is the throw
Error resolved

In the above program, the `throw` statement is used within the `try` block to catch an exception. And the `throw` statement is rethrown in the `catch` block which gets executed if the `catch` block cannot handle the exception.

Here, the `catch` block handles the exception and no error occurs. Hence, the `throw` statement is not rethrown.

If the error was not handled by the catch block, the throw statement would be rethrown with error message Uncaught Error: The value is low

JavaScript Modules
==================

In this tutorial, you will learn about modules in JavaScript with the help of examples.

As our program grows bigger, it may contain many lines of code. Instead of putting everything in a single file, you can use modules to separate codes in separate files as per their functionality. This makes our code organized and easier to maintain.

Module is a file that contains code to perform a specific task. A module may contain variables, functions, classes etc. Let's see an example,

Suppose, a file named **greet.js** contains the following code:

    // exporting a function
    export function greetPerson(name) {
        return `Hello ${name}`;
    }

Now, to use the code of **greet.js** in another file, you can use the following code:

    // importing greetPerson from greet.js file
    import { greetPerson } from './greet.js';

    // using greetPerson() defined in greet.js
    let displayName = greetPerson('Jack');

    console.log(displayName); // Hello Jack

Here,

*   The `greetPerson()` function in the **greet.js** is exported using the `export` keyword

        export function greetPerson(name) {
            ...
        }

*   Then, we imported `greetPerson()` in another file using the `import` keyword. To import functions, objects, etc., you need to wrap them around `{ }`.

        import { greet } from '/.greet.js';


**Note**: You can only access exported functions, objects, etc. from the module. You need to use the `export` keyword for the particular function, objects, etc. to import them and use them in other files.

* * *

Export Multiple Objects
-----------------------

It is also possible to export multiple objects from a module. For example,

In the file **module.js**

    // exporting the variable
    export const name = 'JavaScript Program';

    // exporting the function
    export function sum(x, y) {
        return x + y;
    }

In main file,

    import { name, sum } from './module.js';

    console.log(name);
    let add = sum(4, 9);
    console.log(add); // 13

Here,

    import { name, sum } from './module.js';

This imports both the name variable and the `sum()` function from the **module.js** file.

* * *

Renaming imports and exports
----------------------------

If the objects (variables, functions etc.) that you want to import are already present in your main file, the program may not behave as you want. In this case, the program takes value from the main file instead of the imported file.

#div-gpt-ad-Programizcom37046 {display:none; width: 728px; height: 90px; } #div-gpt-ad-Programizcom36796 {display: block;} @media(min-width: 992px) { #div-gpt-ad-Programizcom37046 {display: block;} #div-gpt-ad-Programizcom36796 {display: none;}}

Ad

To avoid naming conflicts, you can rename these functions, objects, etc. during the export or during the import .

### 1\. Rename in the module (export file)

    // renaming import inside module.js
    export {
        function1 as newName1,
        function2 as newName2
    };

    // when you want to use the module
    // import in the main file
    import { newName1, newName2 } from './module.js';

Here, while exporting the function from **module.js** file, new names (here, newName1 & newName2 ) are given to the function. Hence, when importing that function, the new name is used to reference that function.

* * *

### 2\. Rename in the import file

    // inside module.js
    export {
        function1,
        function2
    };

    // when you want to use the module
    // import in the required file with different name

    import { function1 as newName1, function2 as newName2 } from './module.js';

Here, while importing the function, the new names (here, newName1 & newName2 ) are used for the function name. Now you use the new names to reference these functions.

* * *

Default Export
--------------

You can also perform default export of the module. For example,

In the file **greet.js**:

    // default export
    export default function greet(name) {
        return `Hello ${name}`;
    }

    export const age = 23;

Then when importing, you can use:

    import random_name from './greet.js';

While performing default export,

*   random\_name is imported from `greet.js`. Since, `random_name` is not in `greet.js`, the default export (`greet()` in this case) is exported as `random_name`.
*   You can directly use the default export without enclosing curly brackets `{}`.

**Note**: A file can contain multiple exports. However, you can only have one default export in a file.

* * *

Modules Always use Strict Mode
------------------------------

By default, modules are in [strict mode](/javascript/use-strict). For example,

    // in greet.js
    function greet() {
        // strict by default
    }

    export greet();

* * *

Benefit of Using Module
-----------------------

*   The code base is easier to maintain because different code having different functionalities are in different files.
*   Makes code reusable. You can define a module and use it numerous times as per your needs.

* * *

Array.prototype.indexOf()

Syntax
indexOf(searchElement)
indexOf(searchElement, fromIndex)

Array.indexOf(searchElement, fromIndex)

Example:

const beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

console.log(beasts.indexOf('bison'));
// expected output: 1

// start from index 2
console.log(beasts.indexOf('bison', 2));
// expected output: 4

console.log(beasts.indexOf('giraffe'));
// expected output: -1

const array = [2, 9, 9];
array.indexOf(2);     // 0
array.indexOf(7);     // -1
array.indexOf(9, 2);  // 2
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0

--------
Array.prototype.findIndex()

Syntax
// Arrow function
findIndex((element) => { /* ... */ } )
findIndex((element, index) => { /* ... */ } )
findIndex((element, index, array) => { /* ... */ } )

// Callback function
findIndex(callbackFn)
findIndex(callbackFn, thisArg)

// Inline callback function
findIndex(function(element) { /* ... */ })
findIndex(function(element, index) { /* ... */ })
findIndex(function(element, index, array){ /* ... */ })
findIndex(function(element, index, array) { /* ... */ }, thisArg)
Copy to Clipboard
Parameters
callbackFn
A function to execute on each value in the array until the function returns true, indicating that the satisfying element was found.

The function is called with the following arguments:

element
The current element being processed in the array.

index
The index of the current element being processed in the array.

array
The array findIndex() was called upon.

thisArg Optional
Optional object to use as this when executing callbackFn.

Return value
The index of the first element in the array that passes the test. Otherwise, -1.

Note: if the index of the first element in the array that passes the test is 0, the return value of findIndex will be interpreted as Falsy in conditional statements.

Example:

const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber));
// expected output: 3

function isPrime(num) {
  for (let i = 2; num > i; i++) {
    if (num % i == 0) {
      return false;
    }
  }
  return num > 1;
}

console.log([4, 6, 8, 9, 12].findIndex(isPrime)); // -1, not found
console.log([4, 6, 7, 9, 12].findIndex(isPrime)); // 2 (array[2] is 7)


--------
JavaScript Variables

Using var
Using let
Using const
Using nothing

When to Use JavaScript var?
Always declare JavaScript variables with var,let, orconst.

The var keyword is used in all JavaScript code from 1995 to 2015.

The let and const keywords were added to JavaScript in 2015.

If you want your code to run in older browser, you must use var.

When to Use JavaScript const?
If you want a general rule: always declare variables with const.

If you think the value of the variable can change, use let.

In this example, price1, price2, and total, are variables:

Example
const price1 = 5;
const price2 = 6;
let total = price1 + price2;

Description:

The two variables price1 and price2 are declared with the const keyword.

These are constant values and cannot be changed.

The variable total is declared with the let keyword.

This is a value that can be changed.

Let:

let x = 5;
let y = 6;
Just like in algebra, variables are used in expressions:

let z = x + y;

9.1 Overview
ES6 provides two new ways of declaring variables: let and const, which mostly replace the ES5 way of declaring variables, var.

9.1.1 let
let works similarly to var, but the variable it declares is block-scoped, it only exists within the current block. var is function-scoped.

In the following code, you can see that the let-declared variable tmp only exists inside the block that starts in line A:

function order(x, y) {
    if (x > y) { // (A)
        let tmp = x;
        x = y;
        y = tmp;
    }
    console.log(tmp===x); // ReferenceError: tmp is not defined
    return [x, y];
}
9.1.2 const
const works like let, but the variable you declare must be immediately initialized, with a value that can’t be changed afterwards.

const foo;
    // SyntaxError: missing = in const declaration

const bar = 123;
bar = 456;
    // TypeError: `bar` is read-only
Since for-of creates one binding (storage space for a variable) per loop iteration, it is OK to const-declare the loop variable:

for (const x of ['a', 'b']) {
    console.log(x);
}
// Output:
// a
// b
9.1.3 Ways of declaring variables
The following table gives an overview of six ways in which variables can be declared in ES6 (inspired by a table by kangax):

 	Hoisting	Scope	Creates global properties
var	Declaration	Function	Yes
let	Temporal dead zone	Block	No
const	Temporal dead zone	Block	No
function	Complete	Block	Yes
class	No	Block	No
import	Complete	Module-global	No
9.2 Block scoping via let and const
Both let and const create variables that are block-scoped – they only exist within the innermost block that surrounds them. The following code demonstrates that the const-declared variable tmp only exists inside the block of the if statement:

function func() {
    if (true) {
        const tmp = 123;
    }
    console.log(tmp); // ReferenceError: tmp is not defined
}
In contrast, var-declared variables are function-scoped:

function func() {
    if (true) {
        var tmp = 123;
    }
    console.log(tmp); // 123
}
Block scoping means that you can shadow variables within a function:

function func() {
  const foo = 5;
  if (···) {
     const foo = 10; // shadows outer `foo`
     console.log(foo); // 10
  }
  console.log(foo); // 5
}
9.3 const creates immutable variables
Variables created by let are mutable:

let foo = 'abc';
foo = 'def';
console.log(foo); // def
Constants, variables created by const, are immutable – you can’t assign different values to them:

const foo = 'abc';
foo = 'def'; // TypeError

JavaScript Operators

    Arithmetic Operators
    Comparison (Relational) Operators
    Bitwise Operators
    Logical Operators
    Assignment Operators
    Special Operators

JavaScript Arithmetic Operators
Operator	Description	Example
+	Addition	10+20 = 30
-	Subtraction	20-10 = 10
*	Multiplication	10*20 = 200
/	Division	20/10 = 2
%	Modulus (Remainder)	20%10 = 0
++	Increment	var a=10; a++; Now a = 11
--	Decrement	var a=10; a--; Now a = 9

JavaScript Comparison Operators
The JavaScript comparison operator compares the two operands. The comparison operators are as follows:

Operator	Description	Example
==	Is equal to	10==20 = false
===	Identical (equal and of same type)	10==20 = false
!=	Not equal to	10!=20 = true
!==	Not Identical	20!==20 = false
>	Greater than	20>10 = true
>=	Greater than or equal to	20>=10 = true
<	Less than	20<10 = false
<=	Less than or equal to	20<=10 = false
JavaScript Bitwise Operators
The bitwise operators perform bitwise operations on operands. The bitwise operators are as follows:

Operator	Description	Example
&	Bitwise AND	(10==20 & 20==33) = false
|	Bitwise OR	(10==20 | 20==33) = false
^	Bitwise XOR	(10==20 ^ 20==33) = false
~	Bitwise NOT	(~10) = -10
<<	Bitwise Left Shift	(10<<2) = 40
>>	Bitwise Right Shift	(10>>2) = 2
>>>	Bitwise Right Shift with Zero	(10>>>2) = 2
JavaScript Logical Operators
The following operators are known as JavaScript logical operators.

Operator	Description	Example
&&	Logical AND	(10==20 && 20==33) = false
||	Logical OR	(10==20 || 20==33) = false
!	Logical Not	!(10==20) = true
JavaScript Assignment Operators
The following operators are known as JavaScript assignment operators.

Operator	Description	Example
=	Assign	10+10 = 20
+=	Add and assign	var a=10; a+=20; Now a = 30
-=	Subtract and assign	var a=20; a-=10; Now a = 10
*=	Multiply and assign	var a=10; a*=20; Now a = 200
/=	Divide and assign	var a=10; a/=2; Now a = 5
%=	Modulus and assign	var a=10; a%=2; Now a = 0
JavaScript Special Operators
The following operators are known as JavaScript special operators.

Operator	Description
(?:)	Conditional Operator returns value based on the condition. It is like if-else.
,	Comma Operator allows multiple expressions to be evaluated as single statement.
delete	Delete Operator deletes a property from the object.
in	In Operator checks if object has the given property
instanceof	checks if the object is an instance of given type
new	creates an instance (object)
typeof	checks the type of object.
void	it discards the expression's return value.
yield	checks what is returned in a generator by the generator's iterator.
