## Background
These are notes that I believe are fundamentals and I should eventually move to notecards to help remember easier.

Each bullet point refers to a single notecard that could be created.

## Notes

- Javascript versioning is denoted with "ES", so ES1, ES2, etc. ES14 is the current version which is the released version from 2023 (so ES2023 is the same thing)
- To add javascript to an html page, you use the `<script>` tag. Inside the tag, you can insert your javascript code.
- There are three ways to declare a variable in javascript: `var`, `let`, and `const`. `var` is global by default and can be re-assigned. `let` is block scoped by default (like Java and C++ variables) and `const` is block scoped but also the value cannot be re-assigned. Use `const` over `let` over `var` always.
- Javascript "hoisting" is a concept where the code after going through the interpreter is re-arranged, so what happens under the hood is different than what is seen in the code. More specifically, variable instantiations always happen at the top, then assignments happen where they were written. For example:
```js
console.log(hoist); // Output: undefined

var hoist = 'The variable has been hoisted.';
```
under the hood after the interpreter becomes:
```js
var hoist;

console.log(hoist); // Output: undefined
hoist = 'The variable has been hoisted.';
```
- Note: using `let` and `const` fixes this issue as they were introduced in ES6. If you use them, referencing the variable results in a "Output: ReferenceError: hoist is not defined" now.
- Same thing happens with functions so you can call a function before it is defined since hoisting will bring that function declaration to the top of the file after the interpreter.
- However, function expressions so function variables essentially do not get hoisted.
- Variable assignment > Function Declaration and Function Declaration > Variable declaration
For example:
```js
var double = 22;

function double(num) {
  return (num*2);
}

console.log(typeof double); // Output: number
```
- Classes are the same as function declarations in JS. So if you try to use a class, but the class was defined below the line, then it won't know what that class is.
- Javascript is like Python, all variables are determined at runtime and can change. You can determine the type of a variable by using  `typeof`. For example: `typeof 42` returns number.
- These are all the "types" in javascript: `undefined`, `object` (null), `boolean`, `number`, `bigint`, `string`, `symbol`, `function`, `object` (any other type)
- Note, when using typeof, these are need to be surrounded with **quotation marks**. For example:
- `typeof true === "boolean";` evaluates to true. 
- `typeof new Date() === "object";`
- `typeof function () {} === "function";
- `typeof class C {} === "function"; 
- `typeof 3.14 === "number";
- Tricky ones:
- `typeof NaN === "number"; // Despite being "Not-A-Number"
- `typeof Infinity === "number";
- `typeof new Boolean(true) === "object"; // don't do this
- If you assign a value to a variable that has not been declared, such as `potato = true` it will automatically become a **global variable**.
`
