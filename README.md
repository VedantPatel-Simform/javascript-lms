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

### **Variables and Data Types**

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
  const c = 30;
  // c = 40; // TypeError: Assignment to constant variable.
  console.log(c); // 30
}
exampleConst();
```
