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

### 1. **Variables and Data Types**

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
