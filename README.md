# javascript-lms

## Javascript basics

### What is javascript ?
- Javascript is a progamming language that is used to create interactive and dynamic websites over the internet .
- It is executed on browser , which is done by javascript engines present in the browser.
  - Google: `V8 ENGINE`
  - Edge (Internet Explorer) :	`Chakra`
  - Firefox : `Spider Monkey`
- After the creation of Node.js, it can also be executed on server using Runtime enviornment that embeds the Browser engine into a c++ enviornment to allow it to execute code on server side

### Characteristics of Javascript

1. **Interpreted Language**  
   JavaScript is an interpreted language, meaning the code is executed line-by-line by the browser or runtime environment (like Node.js). This provides flexibility and ease of development since you don't need to compile the code before running it.

2. **Dynamically Typed**  
   In JavaScript, you don't have to declare the type of a variable. The type is determined at runtime, which makes the language flexible but also requires careful handling of data types to avoid unexpected behaviors.

3. **Weakly Typed**  
   JavaScript automatically converts between different data types when necessary, which can sometimes lead to unexpected results. For example, adding a string and a number might result in string concatenation rather than numeric addition.

4. **Object-Oriented**  
   JavaScript supports object-oriented programming (OOP). You can create objects and use properties and methods to model real-world entities. JavaScript also supports inheritance via prototypes.

5. **Event-Driven**  
   JavaScript is commonly used in an event-driven programming style, especially in web development. Events like clicks, form submissions, or keyboard presses trigger JavaScript functions that handle the response dynamically.

6. **Asynchronous**  
   JavaScript allows asynchronous programming using features like callbacks, promises, and async/await. This allows for non-blocking code execution, which is especially useful for tasks like fetching data from an API or waiting for user input.

7. **Single-Threaded**  
   JavaScript is single-threaded, meaning it can only execute one operation at a time. However, its event-driven and non-blocking nature allows for efficient handling of multiple tasks without locking up the browser or application.

8. **Cross-Platform**  
   JavaScript runs on all modern web browsers, making it highly cross-platform. With Node.js, it can also be used for server-side programming, enabling full-stack JavaScript applications.

9. **Versatile**  
   JavaScript is a versatile language used for both client-side and server-side development. It can be used for web applications, mobile apps (via frameworks like React Native), and even desktop applications (using Electron).

### Java vs JavaScript: Key Differences

| Feature              | **Java**                                    | **JavaScript**                              |
|----------------------|---------------------------------------------|---------------------------------------------|
| **Type**             | Compiled, statically typed, object-oriented | Interpreted, dynamically typed, prototype-based |
| **Primary Use**      | Backend development, mobile (Android), desktop apps | Frontend web development, also backend (Node.js) |
| **Execution**        | Runs on JVM (Java Virtual Machine)          | Runs directly in browsers or with Node.js   |
| **Syntax**           | More complex, similar to C/C++              | Simpler, more flexible                      |
| **Concurrency**      | Multi-threading                             | Single-threaded with asynchronous handling |
| **Platform**         | Cross-platform via JVM                     | Runs on all modern browsers, cross-platform with Node.js |

### Static Typing vs Dynamic Typing

| Feature              | **Static Typing**                                    | **Dynamic Typing**                                  |
|----------------------|------------------------------------------------------|-----------------------------------------------------|
| **Definition**        | Variable types are known at compile-time.            | Variable types are determined at runtime.           |
| **Example**           | `int number = 10;`                                   | `let number = 10;`                                  |
| **Language Example**  | Java, C, C++                                        | JavaScript, Python, Ruby                           |
| **Advantages**        | Faster error detection, better performance, type safety. | More flexible, easier to write code quickly.        |
| **Disadvantages**     | Requires more effort to manage types, less flexibility. | Errors may only be caught at runtime, potential type issues. |

### Weakly Typed vs Strongly Typed

| Feature              | **Weakly Typed**                                   | **Strongly Typed**                                  |
|----------------------|----------------------------------------------------|-----------------------------------------------------|
| **Definition**        | The language performs implicit type conversions (type coercion). | Variables are strictly defined and no automatic type conversion occurs. |
| **Example**           | `let result = "10" + 5; // Result: "105"`           | `let result = "10" + 5; // Error in strongly typed languages` |
| **Language Example**  | JavaScript, PHP                                    | Java, Python, Swift                                 |
| **Advantages**        | More flexible, convenient for quick coding.        | Fewer bugs, better error handling, clearer code.    |
| **Disadvantages**     | Type coercion can lead to unexpected behavior.     | Requires more explicit type definitions.            |

---

## JavaScript Engine Overview
   - JavaScript is executed by engines like V8, which consist of two main components:
     - **Memory Heap**: Where memory allocation happens.
     - **Call Stack**: Where the execution context is managed.

### Execution Phases
JavaScript execution can be broken down into two main phases:

#### 1. Memory Allocation Phase (Creation Phase)
   - **Creation of Global Execution Context**:
     - The JavaScript engine first creates the **Global Execution Context**.
     - It includes two components:
       - **Memory Component (Variable Environment)**: 
         - All variables and functions are stored in memory.
         - Variables are initialized with `undefined`, and function declarations are fully hoisted.
       - **Code Component (Thread of Execution)**: 
         - The engine prepares to execute the code line by line.
   
   **Hoisting** occurs here, where variables and functions are moved to the top of their scope in memory.

#### 2. Code Execution Phase
   - After memory allocation, the code execution phase begins:
     - **Execution Context**: JavaScript starts executing code line by line.
     - Variables are assigned actual values.
     - Function calls create new **execution contexts**.

### Execution Context
Each function call creates a new execution context, which is added to the **Call Stack**.

- **Components of an Execution Context**:
  - **Variable Environment**: Memory allocation for variables within the function.
  - **Lexical Environment**: Memory and environment for the outer variables accessible to the function.
  - **`this` Binding**: The value of `this` in the context.

When a function is called, it stores its local variables and parameters in the execution context.

### Call Stack
   - The **Call Stack** is used to manage execution contexts.
   - When a function is called, its execution context is pushed onto the call stack.
   - Once the function execution is complete, its context is popped from the stack.

The call stack manages the order of function execution, pushing and popping contexts as functions are called and return.

### Asynchronous Code and Event Loop
   - JavaScript handles asynchronous operations using the **Event Loop** and **Task Queue**.
   - Asynchronous code (e.g., timers, Promises) is placed in the task queue, and once the call stack is clear, the event loop pushes tasks from the queue to the stack for execution.

The event loop continuously checks the call stack and the task queue, ensuring that asynchronous operations are executed after the synchronous code has completed.

### Summary
   - **Memory Allocation Phase**: Variables are hoisted, functions are stored.
   - **Code Execution Phase**: Code runs line by line; function calls are managed using the call stack.
   - **Call Stack**: Tracks function calls and execution contexts.
   - **Event Loop**: Handles asynchronous tasks by moving them from the task queue to the call stack.

## Hoisting in JS

In JavaScript, hoisting refers to the behavior where variable and function declarations are moved to the top of their containing scope during the compile phase, before the code is executed. This can sometimes lead to unexpected results if you're not aware of how it works.

To break it down:

### **Variable Hoisting:**

- var declarations are hoisted, but only the declaration, not the assignment. They are hoisted with `undefined` value untill assignment.
- This means the variable is accessible before the point it's initialized, but its value is undefined until the assignment happens.
- let and const are also hoisted, but with a key difference: they are in a "temporal dead zone" from the start of the block until they are initialized. Accessing them before initialization results in a ReferenceError.
  
Example with var:

```javascript
console.log(a); // undefined
var a = 5;
console.log(a); // 5
```
Example with let/const:
```javascript
console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 10;
```
#### TDZ (Temporal Dead Zone) for `let` and `const`
TDZ (Temporal Dead Zone) refers to the period between the entering of a scope and the initialization of variables declared with let and const. During this time, accessing those variables results in a ReferenceError.

**Key Points:**
Only let and const have TDZ; var does not.
Variables are hoisted but not initialized, so they cannot be accessed until their declaration is evaluated.
It prevents accidental use of uninitialized variables, improving code reliability.
Example:
```javascript
console.log(x); // ReferenceError: Cannot access 'x' before initialization
let x = 10;
```
**Why It Matters:**
TDZ ensures variables are not used before they are assigned, avoiding bugs and enhancing predictability in JavaScript.

Like, if the block is starting from line 5 and the variable is declared with `let` on line number 9, then the lines 5-8 are TDZ. Between lines 5 and 8, trying to access x will result in a `ReferenceError` because the variable is not initialized yet.

### **Function Hoisting:**

Function declarations are hoisted in their entirety, meaning you can call the function before it's defined in the code.
Function expressions (including arrow functions) are not hoisted. Only the variable is hoisted, not the function assignment.
Example with function declaration:

```javascript
myFunction(); // "Hello"
function myFunction() {
    console.log("Hello");
}
```
Example with function expression:

```javascript
greet(); // TypeError: greet is not a function
var greet = function() {
    console.log("Hello");
};
```
#### **Key takeaways for the interview:**
- var hoists only declarations, and the value is undefined until assignment.
- let/const hoist the declarations but remain in the temporal dead zone until initialized.
- Function declarations are hoisted fully (you can call them before declaration), whereas function expressions (including arrow functions) are only hoisted by the variable declaration.
- Understanding hoisting is essential for avoiding subtle bugs and writing cleaner, more predictable code in JavaScript.

## **Variables and Data Types**

- **Primitive Types**: `string`, `number`, `boolean`, `undefined`, `null`, `symbol`, `bigint`.
- **Non-Primitive Types**: `object` (including arrays and functions).

**Example:**
```javascript
let name = "John";      // string
let age = 25;           // number
let isActive = true;    // boolean
let user = { name, age }; // object
let largeNumber = 1234567890123456789012345678901234567890n; // bigInt
let sym = Symbol('description'); // Represents a unique identifier
```
- **Non-Primitive Types**
  - Object: Collection of key-value pairs.
  - Array: Ordered list of values.
  - Function: Reusable code block.
  - Date: Date and time representation.
  - RegExp: Pattern for matching strings.

```javascript
//non-primitive type

const obj = {id : 1}
const arr = [1,2,3,4]
function abc(){} 
```
### Tricky JavaScript Interview Questions with Answers

```javascript
// 1. Check if NaN is strictly equal to undefined
console.log(NaN === undefined);  // false, NaN and undefined are different types and values

// 2. Check if NaN is loosely equal to undefined
console.log(NaN == undefined);  // false, NaN is not loosely equal to undefined

// 3. Check if null is loosely equal to NaN
console.log(null == NaN);  // false, null and NaN are different values

// 4. Check if null is strictly equal to NaN
console.log(null === NaN);  // false, null and NaN are different types

// 5. Check if null is loosely equal to undefined
console.log(null == undefined);  // true, null and undefined are loosely equal

// 6. Check if null is strictly equal to undefined
console.log(null === undefined);  // false, null is an object and undefined is a type

// 7. Check if null is strictly equal to null
console.log(null === null);  // true, null is strictly equal to null

// 8. Check if undefined is strictly equal to undefined
console.log(undefined === undefined);  // true, both are of the same type and value

// 9. Check if NaN is strictly equal to NaN
console.log(NaN === NaN);  // false, NaN is not equal to itself in JavaScript

// 10. Check if 0 is loosely equal to false
console.log(0 == false);  // true, 0 is loosely equal to false because of type coercion

// 11. Check if "" (empty string) is loosely equal to false
console.log("" == false);  // true, empty string is loosely equal to false

// 12. Check if 0 is strictly equal to false
console.log(0 === false);  // false, 0 is a number and false is a boolean

// 13. Check if an empty object is loosely equal to null
console.log({} == null);  // false, an empty object is not equal to null

// 14. Check if an empty object is strictly equal to null
console.log({} === null);  // false, objects and null are different types

// 15. Check if an array is loosely equal to an object
console.log([] == {});  // false, empty array and empty object are different

// 16. Check if an empty array is loosely equal to false
console.log([] == false);  // true, empty array is loosely equal to false

// 17. Check if an empty array is strictly equal to false
console.log([] === false);  // false, array and boolean are different types

// 18. Check if '5' + 1 results in a number or string
console.log("5" + 1);  // "51", string concatenation happens, result is a string

// 19. Check if '5' - 1 results in a number or string
console.log("5" - 1);  // 4, string '5' is coerced to a number for subtraction

// 20. Check if 1 / 0 results in Infinity
console.log(1 / 0);  // Infinity, dividing by zero results in Infinity in JavaScript

// 21. Check if typeof NaN is 'number'
console.log(typeof NaN);  // "number", NaN is considered a type 'number' in JavaScript

// 22. Check if undefined is equal to null using strict equality
console.log(undefined === null);  // false, undefined and null are different types

// 23. Check if +undefined results in NaN
console.log(+undefined);  // NaN, unary plus attempts to convert undefined to a number, results in NaN

// 24. Check if 'true' is loosely equal to true
console.log("true" == true);  // false, string "true" is not the same as boolean true

// 25. Check if a string with a number in it ('10') is loosely equal to a number (10)
console.log("10" == 10);  // true, string "10" is coerced to number 10 before comparison

// 26. type of null & undefined
console.log(typeof undefined); // undefined 
console.log(typeof null); // object
```

### Differences between `var`, `let`, and `const`

| Feature            | `var`                                  | `let`                       | `const`                     |
| ------------------ | -------------------------------------- | --------------------------- | --------------------------- |
| **Scope**          | Function-scoped                        | Block-scoped                | Block-scoped                |
| **Hoisting**       | Hoisted and initialized to `undefined` | Hoisted but not initialized | Hoisted but not initialized |
| **Re-declaration** | Allowed                                | Not allowed                 | Not allowed                 |
| **Re-assignment**  | Allowed                                | Allowed                     | Not allowed                 |

### Examples

#### `var`

```javascript
function exampleVar() {
  console.log(a); // undefined
  var a = 10;
  console.log(a); // 10
}
exampleVar();
```
#### `let`
```javascript
function exampleLet() {
  // console.log(b); // ReferenceError: b is not defined
  let b = 20;
  console.log(b); // 20
}
exampleLet();
```
#### `const`
```javascript
function exampleConst() {
const a; //Syntax Error: missing initializer
  const c = 30;
  // c = 40; // TypeError: Assignment to constant variable.
  console.log(c); // 30
}
exampleConst();
```
### Type coersion and Type conversion
**Type coercion**, refers to the automatic or implicit conversion of values from one data type to another (such as strings to numbers). 

For example:
```javascript
console.log('5' - 3); // 2 (string '5' is converted to number 5)
```
**Type conversion**, on the other hand, is the explicit transformation of values from one data type to another by the developer using methods or operators:

```javascript
console.log(Number('5') + 3); // 8 (string '5' is explicitly converted to number 5)
```

#### examples
```javascript
// String to Number Coercion vs Conversion
console.log('5' - 2); // 3 (coercion: string '5' is coerced to number 5)
console.log(Number('5') - 2); // 3 (conversion: string '5' is explicitly converted to number 5)

// Number to String Coercion vs Conversion
console.log('5' + 2); // '52' (coercion: number 2 is coerced to string '2')
console.log(String(5) + 2); // '52' (conversion: number 5 is explicitly converted to string '5')

// Boolean to Number Coercion vs Conversion
console.log(true + 1); // 2 (coercion: boolean true is coerced to number 1)
console.log(Number(true) + 1); // 2 (conversion: boolean true is explicitly converted to number 1)

// Null to Number Coercion vs Conversion
console.log(null + 5); // 5 (coercion: null is coerced to number 0)
console.log(Number(null) + 5); // 5 (conversion: null is explicitly converted to number 0)

// Boolean to String Coercion vs Conversion
console.log(true + ' is true'); // 'true is true' (coercion: boolean true is coerced to string 'true')
console.log(String(true) + ' is true'); // 'true is true' (conversion: boolean true is explicitly converted to string 'true')

// Number to Boolean Coercion vs Conversion
console.log(Boolean(0)); // false (conversion: number 0 is explicitly converted to false)
console.log(!0); // true (coercion: using ! coerces 0 to false and then negates it to true)
```

## Operators in JavaScript

#### 1. Arithmetic Operators
These operators perform basic arithmetic operations.

| Operator | Description        | Example        |
|----------|--------------------|----------------|
| `+`      | Addition           | `5 + 3` → `8`  |
| `-`      | Subtraction        | `5 - 3` → `2`  |
| `*`      | Multiplication     | `5 * 3` → `15` |
| `/`      | Division           | `6 / 3` → `2`  |
| `%`      | Modulus (Remainder)| `5 % 3` → `2`  |
| `**`     | Exponentiation     | `2 ** 3` → `8` |

#### 2. Comparison Operators
These operators compare two values and return a boolean result.

| Operator | Description        | Example        |
|----------|--------------------|----------------|
| `==`     | Equal to           | `5 == '5'` → `true` |
| `===`    | Strict Equal to    | `5 === '5'` → `false` |
| `!=`     | Not Equal to       | `5 != 3` → `true` |
| `!==`    | Strict Not Equal to| `5 !== 3` → `true` |
| `>`      | Greater than       | `5 > 3` → `true` |
| `<`      | Less than          | `5 < 3` → `false` |
| `>=`     | Greater than or equal to | `5 >= 3` → `true` |
| `<=`     | Less than or equal to    | `5 <= 3` → `false` |

#### 3. Logical Operators
These operators are used to combine multiple conditions.

| Operator | Description        | Example               |
|----------|--------------------|-----------------------|
| `&&`     | Logical AND        | `(5 > 3) && (8 > 5)` → `true` |
| `\|\|`   | Logical OR         | `(5 > 3) \|\| (2 > 3)` → `true` | 
| `!`      | Logical NOT        | `!(5 > 3)` → `false`  |

#### 4. Assignment Operators
These operators are used to assign values to variables.

| Operator | Description        | Example         |
|----------|--------------------|-----------------|
| `=`      | Assignment         | `let x = 5;`    |
| `+=`     | Add and assign     | `x += 5;` → `x = x + 5` |
| `-=`     | Subtract and assign| `x -= 5;` → `x = x - 5` |
| `*=`     | Multiply and assign| `x *= 5;` → `x = x * 5` |
| `/=`     | Divide and assign  | `x /= 5;` → `x = x / 5` |
| `%=`     | Modulus and assign | `x %= 5;` → `x = x % 5` |

#### 5. Ternary Operator
The ternary operator is a shorthand for `if-else` statements.

| Syntax                | Example                      |
|-----------------------|------------------------------|
| `condition ? expr1 : expr2` | `let result = (5 > 3) ? 'Yes' : 'No';` → `'Yes'` |

## Conditional Statements in JS

- Conditional statements in JavaScript are used to perform different actions based on different conditions. JavaScript supports several types of conditional statements to control the flow of execution based on specific conditions.

### **if Statement**

The if statement is used to execute a block of code only if a specified condition is true.

Syntax:
```javascript
if (condition) {
    // block of code to be executed if the condition is true
}
```
### **if...else Statement**

The if...else statement is used to execute one block of code if the condition is true and another block of code if the condition is false.

Syntax:
```javascript
if (condition) {
    // block of code to be executed if the condition is true
} else {
    // block of code to be executed if the condition is false
}
```
### **if...else if...else Statement**

The if...else if...else statement is used to test multiple conditions. If the first condition is false, the next else if statement is checked, and so on. If none of the conditions are true, the else block is executed.

Syntax:
```javascript
if (condition1) {
    // block of code to be executed if condition1 is true
} else if (condition2) {
    // block of code to be executed if condition2 is true
} else {
    // block of code to be executed if none of the conditions are true
}
```
### **switch Statement**

The switch statement is used to perform different actions based on different conditions. It is a more convenient way to test for multiple values of a single expression.

Syntax:
```javascript
switch (expression) {
    case value1:
        // block of code to be executed if expression === value1
        break;
    case value2:
        // block of code to be executed if expression === value2
        break;
    default:
        // block of code to be executed if none of the cases match
}
```
### **Ternary Operator**

The ternary operator is a shorthand way to write conditional statements. It is used as a one-liner if-else statement.

Syntax:
```javascript
condition ? expressionIfTrue : expressionIfFalse;
```
### **Summary**

- if statement executes code if a condition is true.
- if...else statement executes one block of code if a condition is true, and another if it is false.

- if...else if...else statement checks multiple conditions.

- switch statement is used for multiple conditions based on a single expression.

- Ternary operator is a shorthand for if...else statements.

## Functions in JS

A function in JS is a block of reusable code designed to perform a specific task. Functions help in organizing code, making it more readable, and promoting code reuse.

### 1. Function Declaration
A function declaration is the classic way to define a function in JavaScript.

```javascript
function greet(name) {
  console.log(`Hello, ${name}!`);
}
greet("Alice"); // Output: Hello, Alice!
```
**Important Points:**
- **Hoisting**: Function declarations are hoisted entirely. This means you can call the function before it's defined in the code.
- It’s a straightforward, reusable way to define functions.

### 2. Function Expression
A function expression involves assigning a function to a variable. It can be anonymous or named.

```javascript
const greet = function(name) {
  console.log(`Hello, ${name}!`);
};

greet("Bob"); // Output: Hello, Bob!
```
**Important Points:**

- Function expressions are **not hoisted**. The function can only be called after it's assigned to the variable.
- Commonly used for callbacks, anonymous functions, or assigning functions to variables.
- In case of declaring with `var`, it is undefined untill it is assigned to the function.
- In case of `let` and `const`. It gives `ReferenceError` when it is accessed before it is assigned.

### 3. Arrow Functions
Arrow functions provide a more concise syntax, and they don't have their own this — they inherit it from the surrounding context.

```javascript
const greet = (name) => {
  console.log(`Hello, ${name}!`);
};
greet("Charlie"); // Output: Hello, Charlie!
```
**Important Points:**

- Shorter syntax: Arrow functions are syntactically cleaner, especially for short functions.
- No this binding: this refers to the context of where the arrow function was defined, not where it’s invoked.
- Implicit return: When the function body is a single expression, the return keyword is implied.

```javascript
const add = (a, b) => a + b;
```
### 4. Parameters and Arguments
- Parameters are the names defined in the function signature.
- Arguments are the values passed to the function when it's called.

```javascript
function add(a, b) {
  return a + b;
}
add(2, 3); // Arguments: 2 and 3
```
**Important Points:**

- **Rest Parameters**: You can use the `...` syntax to capture all arguments into an array.

```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3)); // Output: 6
```
- **Arguments object**: For traditional functions, there’s an arguments object which holds all passed arguments, even if they aren't defined as parameters. 
- However, **arrow functions do not have this object**.
```javascript
function showArguments() {
    console.log(arguments);
    console.log(...arguments);
    console.log(arguments[0]);
}
showArguments(1, 2, 3, 'hello');

//Output:
//[Arguments] { '0': 1, '1': 2, '2': 3, '3': 'hello' }
//1 2 3 hello
//1
```
### 5. Default Parameters
JavaScript allows you to specify default values for parameters if they’re not provided.

```javascript
function greet(name = "Guest") {
  console.log(`Hello, ${name}!`);
}
greet();         // Output: Hello, Guest!
greet("Alice");  // Output: Hello, Alice!
```
**Important Points:**

Default parameters are evaluated when the function is called, so they can even be expressions.
```javascript
function add(a, b = a + 1) {
  return a + b;
}
```

### Function declaration vs Expression
| Feature                     | **Function Declaration**                                   | **Function Expression**                                      |
|-----------------------------|-------------------------------------------------------------|--------------------------------------------------------------|
| **Definition**               | A function defined using the `function` keyword outside of any expression. | A function defined as part of an expression, typically assigned to a variable. |
| **Syntax**                   | `function myFunction() { ... }`                             | `var myFunction = function() { ... };`                        |
| **Hoisting**                 | **Hoisted**: Function declarations are hoisted to the top of their scope, making them accessible even before they are defined. | **Not Hoisted**: Function expressions are not hoisted, meaning they are accessible only after the definition. |
| **Usage**                    | Can be called before it appears in the code.                | Must be assigned to the variable before being called.         |
| **Example**                  | `function greet() { console.log("Hello!"); }`               | `var greet = function() { console.log("Hello!"); };`         |
| **Can be Anonymous**         | No, the function must have a name.                          | Yes, function expressions can be anonymous (unnamed).         |
| **Can Be Used for Recursion**| Yes, can be used recursively, since it’s hoisted.            | Not directly, because it’s assigned to a variable and the variable is not hoisted. |
| **Type**                     | It’s a declaration and is a part of the **JavaScript syntax**. | It’s an expression and is evaluated at runtime.               |


## IIFE (Immediately Invoked Function Expressions)

### Why and When to Use IIFE?

#### 1. Avoid Global Namespace Pollution:
The primary use case of an IIFE is to avoid polluting the global namespace. Variables defined inside an IIFE are not accessible outside of it, helping maintain cleaner and more modular code.

**Interview Insight**: You should highlight how IIFEs prevent variable leakage and keep global variables safe from accidental overwrites.

#### 2. Encapsulation (Creating a Module):
IIFEs are widely used in the **Module Pattern**, where the internal implementation details are hidden and only the required public methods or variables are exposed.

**Interview Insight**: Emphasize how IIFEs allow developers to create isolated private states for variables and methods, ideal for data encapsulation.

#### 3. Initialization Code:
An IIFE is great for running initialization logic that should only execute once and not interfere with the rest of the program.

#### 4. Simulating Block Scope (Prior to ES6):
Before ES6 introduced `let` and `const`, IIFEs were a common workaround to create block-scoped variables using `var`. This helped avoid issues like variable hoisting and leaks in the global scope.

#### 5. Functional Programming & Composition:
IIFEs are useful in **functional programming** to compose functions or to run code in a self-contained manner, reducing side effects and dependencies.

### Interview Questions You Might Face About IIFE:

1. **What’s the difference between a function declaration and a function expression?**
   - A **function declaration** is hoisted to the top of its scope, while a **function expression** (like an IIFE) is not hoisted and is invoked immediately after being defined.

2. **Can an IIFE accept arguments?**
   - Yes, you can pass parameters to an IIFE like any other function.

3. **How does IIFE help in avoiding global scope pollution?**
   - By creating a **local function scope**, IIFE ensures that any variables declared within it are not accessible from outside, which prevents accidental global variable overwrites or conflicts.

4. **When would you not use an IIFE?**
   - IIFEs are less commonly needed in modern JavaScript with block-scoping introduced by `let` and `const` in ES6. But they are still helpful for **isolated initialization logic** or in situations where you need to execute code immediately but don’t want to create unnecessary variables in the global scope.

5. **Is IIFE still relevant in ES6+ with block-scoping?**
   - While ES6 introduced `let` and `const` for block-scoping, IIFEs are still useful for **encapsulating logic**, **creating private variables**, or **organizing code in modular patterns**.
```javascript
// 1. Basic IIFE (Anonymous Function)
(function() {
  console.log("This is a basic IIFE!");
})();

// 2. IIFE with Parameters
(function(name) {
  console.log("Hello, " + name + "!");
})("Alice");

// 3. Named IIFE
(function myIIFE() {
  console.log("This is a named IIFE.");
})();

// 4. IIFE Returning a Value
var result = (function(a, b) {
  return a + b;
})(5, 10);
console.log("Result of addition:", result);  // Output: Result of addition: 15

// 5. IIFE for Initialization
(function() {
  var apiKey = "12345";  // Private initialization logic
  console.log("API initialized with key:", apiKey);
})();

// 6. IIFE for Simulating Block Scope (Before ES6)
(function() {
  var blockScopedVar = "I am block-scoped!";
  console.log(blockScopedVar);  // Output: I am block-scoped!
})();
```
## Closure in JavaScript

A closure in JavaScript is a function that "remembers" its lexical scope, even when the function is executed outside that scope. This means that an inner function can access variables from its outer function even after the outer function has completed execution.

Closures are created when a function is defined inside another function, and they allow the inner function to access the variables and parameters of the outer function. This is particularly useful for data encapsulation, maintaining state, and creating function factories or callback functions.

For example, closures are commonly used for:
- Data privacy (keeping variables private)
- Callbacks and asynchronous operations (e.g., event handlers or setTimeout)
- Function factories (where the inner function retains access to parameters passed to the outer function)
Usecase:
- Closures allow you to create private variables that cannot be accessed directly from outside the function, but can be accessed and modified by inner functions. This is similar to private methods or properties in object-oriented languages.

Example:
```javascript
function counter(abc){
    let count = 0;
    return {
        increment: () => {
            count++;
            abc++;
        },
        getValue: function () {
            console.log(count, " ", abc);
        }
    }
}
let count = 1000
const obj = counter(20)

obj.increment()
obj.getValue()

obj.increment()
obj.getValue()

obj.increment()
obj.getValue()

obj.increment()
obj.getValue()

// 1   21
// 2   22
// 3   23
// 4   24
```
  
