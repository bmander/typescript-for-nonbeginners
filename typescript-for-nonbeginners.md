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
## Verifying Your Setup
#### Running a Sample JavaScript Program
#### Compiling and Running a Sample TypeScript Program

## JavaScript Refresher
### Basic Syntax and Concepts
#### Variables and Constants
##### var, let, and const
##### Scope and hoisting
#### Data Types
##### Primitive Types: number, string, boolean, null, undefined, symbol
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

