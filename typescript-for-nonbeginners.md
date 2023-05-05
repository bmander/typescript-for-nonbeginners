# Typescript for nonbeginners: a primer for experienced programmers

## Introduction
### Explanation of TypeScript and its relationship to JavaScript
### Overview of the Primer

## Setting Up Your Environment
### Installing Node.js and npm

**Node.js** is a runtime environment that lets you execute JavaScript code outside of a browser. This makes it possible to run JavaScript on your server or on your machine, just like you would run a Python or C++ script.

**npm**, which stands for Node Package Manager, is the default package manager for Node.js. It allows you to install and manage packages (libraries, frameworks, tools, etc.) that your JavaScript or TypeScript projects might need. It's a crucial tool for modern JavaScript development.

To install Node.js and npm, you can use the package manager for your specific Linux distribution.
* For Debian-based distributions like Ubuntu, you can use `apt`:
  ```
  sudo apt update
  sudo apt install nodejs npm
  ```
* For Red Hat-based distributions like CentOS or Fedora, you can use `dnf`:
  ```
  sudo dnf install nodejs npm
  ```
* For Arch-based distributions, you can use pacman:
  ```
  sudo pacman -Sy nodejs npm
  ```

After installation, verify that Node.js and npm were correctly installed by checking their versions:
```
node -v
npm -v
```

These commands should return the installed versions of Node.js and npm respectively. If you see version numbers, that means Node.js and npm are successfully installed and ready to use.

Remember that Node.js development moves quickly, so you'll want to update Node.js and npm frequently to ensure you have the latest features and security patches. You can use the same commands used for installation to update these tools.
### Setting Up a Code Editor
#### Installing and Setting Up Visual Studio Code
To install Visual Studio Code on a Linux machine, you can download it from the official website or install it through your distribution's package manager.

To install VS Code on Debian-based distributions like Ubuntu, use the following commands:
```
sudo apt update
sudo apt install code
```
For other distributions, please refer to the official Visual Studio Code documentation.

Once installed, you can open VS Code by typing code in your terminal.
#### Installing Useful Extensions for JavaScript and TypeScript Development
VS Code has a robust marketplace for extensions, which can enhance your development experience. Here are a few extensions you might find helpful:
* **ESLint**: ESLint is a static code analysis tool for identifying problematic patterns found in JavaScript code. It's a great tool to ensure your code adheres to a specific coding style.
* **Prettier - Code formatter**: Prettier is an opinionated code formatter that integrates with VS Code. It helps to maintain a consistent code style by automatically formatting your code.
* **Visual Studio IntelliCode**: IntelliCode provides AI-assisted code recommendations based on best practices from thousands of open source repos.

To install an extension, click on the Extensions view icon on the Sidebar (or press `Ctrl+Shift+X`), then search for the extension you want and click on Install.
### Installing TypeScript
#### Explanation of the TypeScript Compiler
TypeScript is a superset of JavaScript that adds static type definitions. It provides the ability to use features from recent versions of JavaScript and some additional features that are not available in JavaScript, such as interfaces and enums.

However, browsers and Node.js understand JavaScript, not TypeScript. That's where the TypeScript compiler (`tsc`) comes in. The TypeScript compiler takes your TypeScript code (`.ts` files) and compiles it down to JavaScript code (`.js` files). This process is known as "transpilation".

The TypeScript compiler also checks your code for errors before it's run, which is a significant advantage over JavaScript. This allows you to catch and fix errors during development rather than runtime.
#### Instructions for Installation via npm
Now that we have Node.js and npm set up, installing TypeScript is straightforward. You can install TypeScript globally on your machine by running the following command in your terminal:
```
sudo npm install -g typescript
```
The `-g` flag stands for "global" and means that TypeScript will be installed globally on your machine, not just in the current directory. This will allow you to use the `tsc` command from anywhere in your system.

After installation, you can verify that TypeScript was correctly installed by checking its version:
```
tsc -v
```
This command should return the installed version of TypeScript. If you see a version number, that means TypeScript is successfully installed and ready to use.

Keep in mind that TypeScript also gets updated regularly, so it's a good idea to update your global TypeScript installation from time to time using the same command you used to install it.
### Verifying Your Setup
#### Running a Sample JavaScript Program
Let's start by running a simple JavaScript program to verify that Node.js is set up correctly. Create a new file named `hello.js` and add the following code:
```javascript
console.log('Hello, JavaScript!');
```
Save the file, then run it using Node.js:
```bash
node hello.js
```
If everything is set up correctly, you should see the message `Hello, JavaScript!` output in your terminal.
#### Compiling and Running a Sample TypeScript Program
Now let's verify that TypeScript is working. Create a new file named `hello.ts` and add the following code:
```typescript
const greeting: string = 'Hello, TypeScript!';
console.log(greeting);
```
This is similar to the JavaScript example, but with TypeScript we can declare the type of our variable. In this case, greeting is a string.

Save the file, then compile it using the TypeScript compiler:
```bash
tsc hello.ts
```
This should create a new file in the same directory named `hello.js`. If you open this file, you'll see that the TypeScript compiler has stripped out the type annotations to produce a JavaScript file:
```javascript
var greeting = 'Hello, TypeScript!';
console.log(greeting);
```
You can now run the compiled JavaScript file using Node.js:
```
node hello.js
```
If everything is set up correctly, you should see the message Hello, TypeScript! output in your terminal.

Congratulations, you've set up and verified your Linux environment for JavaScript and TypeScript development! You're now ready to proceed with the rest of the primer.

## JavaScript Refresher
### Basic Syntax and Concepts
#### Variables and Constants
##### var, let, and const
In JavaScript, you can declare variables using `var`, `let`, or `const`.

```javascript
var x = 5;
let y = 6;
const z = 7;
```

`var` is the oldest way to declare variables. It's not used as much in modern JavaScript, but it's still important to understand. `let` and `const` are newer and were introduced with ES6 (ES2015).

The `let` keyword declares a block-scoped local variable, optionally initializing it to a value. `let` allows you to declare variables that are limited to the scope of a block statement, or expression on which it is used, unlike `var` which defines a variable globally, or locally to an entire function regardless of block scope.

```javascript
let x = 1;
if (true) {
  let x = 2;  // different variable
  console.log(x);  // 2
}
console.log(x);  // 1
```

The `const` keyword behaves like `let`, but you can't reassign to it. It's a good choice when you know a variable shouldn't change:

```javascript
const pi = 3.14159;
pi = 3;  // TypeError: Assignment to constant variable.
```
In comparison, Python uses `=` for variable assignment and doesn't have block scope, and it doesn't have a built-in constant type. In C, you declare variables with a type identifier like `int`, `float`, `char`, etc., and `const` is used to declare constants.
##### Scope and hoisting

In JavaScript, a variable's "scope" is the context in which it's defined. JavaScript has three types of scope: global, function, and block.

* A variable declared outside a function becomes a **global variable** and is accessible from anywhere in your code.
* A variable declared with `var` inside a function is **function-scoped**, meaning it's local to that function and can't be accessed from outside that function.
* A variable declared with `let` or `const` inside a block `{}` is **block-scoped**, meaning it's local to that block.

"Variable hoisting" is a unique feature of JavaScript. The JavaScript interpreter moves all variable and function declarations to the top of their containing scope, but not their assignments. This is called "hoisting". This means you can use a variable before it's declared in your code, although this is considered bad practice and can lead to confusion.

```javascript
console.log(x);  // undefined, but no error because x is "hoisted"
var x = 5;
```

In contrast, Python's scope is determined by the function, class, or module in which a variable is declared, and it doesn't have variable hoisting. In C, a variable's scope is determined by the block in which it's declared, and it also doesn't have variable hoisting.
#### Data Types
JavaScript has a dynamic and weakly typed system, which means you don't have to declare the type of a variable when you create it, and you can change a variable's type later in your code.
##### Primitive Types
JavaScript has seven primitive types: `number`, `string`, `boolean`, `null`, `undefined`, `symbol`, and `bigint`
* `number`: Unlike many other programming languages, JavaScript does not distinguish between integer and floating-point values. All numbers in JavaScript are represented as floating-point values. JavaScript represents numbers using the 64-bit floating-point format defined by the IEEE 754 standard.
  ```javascript
  let count = 10;         // integer
  let weight = 88.6;      // floating-point
  ```
  
  In contrast, Python has separate `int` and `float` types, while C has several number types including `int`, `float`, and `double`.
* `string`: A sequence of characters. Strings in JavaScript are immutable.
  ```javascript
  let message = "Hello, world!";
  ```
  Python and C also have string types, but in C, strings are arrays of characters and are not innately supported as in JavaScript or Python.
* `boolean`: Represents a logical entity and can have two values: `true` or `false`.
  ```javascript
  let isRead = false;
  ```
* `null`: This type also only has one value, `null`. This is usually used to explicitly indicate that a variable should have no value.
  ```javascript
  let empty = null;
  ```
* `undefined`: This type only has one value, `undefined`. A variable that has been declared but has not been assigned a value has the value undefined.
  ```javascript
  let test;
  console.log(test);  // undefined
  ```
  Python raises an error if you try to use a variable that hasn't been assigned. C behavior is undefined if a variable is used before it's assigned.
* `symbol`: Introduced in ES6, a `symbol` is a unique and immutable data type and is often used as an identifier for object properties.
  ```javascript
  let sym = Symbol('description');
  ```
  Neither Python nor C has an equivalent to JavaScript's `symbol`.
* `bigint`: This type was introduced in ES2020 to represent integers of arbitrary length. A `BigInt` is created by appending n to the end of an integer:
  ```javascript
  const bigNumber = 1234567890123456789012345678901234567890n;
  ```
  Neither Python nor C have a direct equivalent to JavaScript's bigint built into the language. In Python, the built-in int type can handle arbitrarily large integers, but they are not the same as JavaScript's bigint because they don't require a special notation. In C, you would need to use a library to work with arbitrarily large integers.
##### Composite Types: object, array, function
#### Control Flow
##### Conditional Statements: if, else, switch
##### Loops: for, while, do...while, for...in, for...of
#### Functions
##### Function Declaration and Expression
##### Arrow Functions
##### Function Parameters and Arguments: default parameters, rest parameters
##### Closures
#### Object-Oriented Programming in JavaScript
##### Objects and Prototypes
##### Classes (ES6+)
### Unique Features and Idiosyncrasies
#### Dynamic Typing and Type Coercion
#### Truthy and Falsy Values
#### The this Keyword
#### Asynchronous JavaScript: Callbacks, Promises, Async/Await
#### Event Loop and Non-blocking I/O
#### Prototypal Inheritance vs. Classical Inheritance
#### JavaScript Module System: CommonJS, AMD, ES6 Modules
#### The Role of Babel and Transpiling ES6+ Code

## TypeScript Basics
### Introduction to Static Typing
#### Contrasting Dynamic Typing in JavaScript and Python
#### Contrasting Static Typing in C
### TypeScript Syntax and Types
#### Basic Types
#### Advanced Types

## TypeScript vs. JavaScript
### How TypeScript Solves JavaScript's Problems
### When to Use TypeScript over JavaScript

## TypeScript vs. Python
### How TypeScript and Python Differ in Approach
### When to Use TypeScript over Python

## TypeScript vs. C
### How TypeScript and C Differ in Approach
### When to Use TypeScript over C

## TypeScript Development Environment
### Setting Up TypeScript
### TypeScript Compiler and Configuration
### Using TypeScript with IDEs

## TypeScript Best Practices
### Typing Strategies
### Code Organization
### Common Pitfalls and How to Avoid Them

## Advanced TypeScript
### Decorators and Metadata Reflection
### Generic Types
### Type Guards and Discriminated Unions

## TypeScript with Libraries and Frameworks
### Using TypeScript with React
### Using TypeScript with Angular
### Using TypeScript with Node.js

## Conclusion
### Recap of TypeScript's Strengths and Use Cases
### Further Resources for Learning

