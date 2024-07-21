# What is JavaScript?

JavaScript is a scripting, high-level, interpreted programming language primarily used to create interactive effects and dynamic content on websites.

# What makes JS unique is :

- Functionality
- Interactivity
- Dynamic websites
- User interaction

# What are the ways to add JS to HTML?

There are 3 ways to add JS to HTML

- Inline JS :
  <br> We are not using inline JS because it is Redundant

```
<body>
  <button onclick="alert('Hello World')">Click Me</button>
</body>;
```

- Internal JS:
  <br> We are not using Internal JS because it is affecting only one page which is again repeated code.

```
<button class="btn">Click Me</button>
<button class="btn">Click Me</button>
<button class="btn">Click Me</button>
<button class="btn">Click Me</button>
<button class="btn">Click Me</button>
<script>
  document.querySelectorAll('.btn').forEach((item)=> {
    item.addEventListener('click', ()=>{
      alert('Hello People');
    })
  });
</script>
```

- External JS:
  <br> The best way of using JS in an HTML file is using external JS file.

```
<script src="./app.js"></script>
```

# What is a statement?

Statement is a set of instructions and will be ended with (;)

# What is Comment?

A comment is a piece of text in the code that is ignored by the interpreter and is used for taking notes or Debugging.

# What are some JavaScript helper methods?

Some JS helper methods are :

- alert()

```
alert("Hello World")
alert({name: 'John'})  //can't show objects
```

- document.write()

```
document.write('Hello World');
document.write({name: 'John'});  //can't show objects
```

- console.log()

```
console.log("Hello World");
console.log({name: 'John'});  //can show objects
```

# What is a variable ?

Variable is a named container used to store and manage data values.
<br> Variables are giving us the options to :

- Store Values
- Access Values
- Modify Values

# Variable Naming Rules :

- Letters are allowed.
- Digits are allowed.
- Underscore is allowed (\_).
- Dollar sign is allowed($).
- Name must start with a letter or \_ or $
- No keywords are allowed.
- Names are case sensitive.
- For the names more than one word we should use camelCase or use (\_).

# let, const and var

### var:

- Scope: Function-scoped (or globally scoped if declared outside a function).
- Hoisting: Variables declared with var are hoisted to the top of their scope and initialized with undefined.
- Re-declaration: Allowed within the same scope.
- Re-assignment: Allowed.

### let :

- Scope: Block-scoped (i.e., limited to the block, statement, or expression where it is declared).
- Hoisting: Variables declared with let are hoisted but not initialized. Accessing them before the declaration results in a ReferenceError (temporal dead zone).
- Re-declaration: Not allowed within the same scope.
- Re-assignment: Allowed.

### const:

- Scope: Block-scoped (same as let).
- Hoisting: Variables declared with const are hoisted but not initialized. Accessing them before the declaration results in a ReferenceError (temporal dead zone).
- Re-declaration: Not allowed within the same scope.
- Re-assignment: Not allowed (the variable reference is constant, though object properties can still be modified).

# JavaScript Escaping Characters:

- Single Quotes `(\')`:

```
var singleQuoted = 'It\'s a nice day.';
```

- Double Quotes `(\")`:

```
var doubleQuoted = "She said, \"Hello!\"";
```

- Backslash `(\\)`:

```
ar backslash = 'This is a backslash: \\';
```

- Newline `(\n)`:

```
var newline = 'Line 1\nLine 2';
```

- Tab `(\t)`:

```
var tab = 'Column 1\tColumn 2';
```

# JavaScript Data Types :

JavaScript is loosely Type Language which means we don't have to specify what type of value will be stored in the variable.
Data types are categorized into two main groups:

- Primitive data types:

  - Number
  - String,
  - Boolean
  - Undefined
  - Null
  - Symbol
  - BigInt

- Object data types:
  - Objects
  - Arrays
  - Functions
  - Date
  - RegExp

# Implicit type converstion

Implicit type conversion in JavaScript refers to the automatic conversion of data types performed by the JavaScript engine without explicit instructions from the developer.

```
If both operands are numbers, the + operator performs arithmetic addition.

If one or both operands are strings, the + operator performs string concatenation.

let num = 10;
let str = "5";
console.log(num + str); // Output: "105"
```

```
JavaScript tries to convert the strings to numbers because subtraction (-) is an arithmetic operator.
'10' is converted to the number 10.
'23' is converted to the number 23.

const value = '10' - '23' // Output: -13

'Anna' can't be converted to the number 10.
'na' can't be converted to the number 23.

const value = "Anna" - "na" // Output:  NaN
```

# Converting a String to a Number

- Using the Number Constructor :

```
let str = "123";
let num = Number(str); // num is now 123
```

- Using the parseInt Function:

```
let str = "123";
let num = parseInt(str, 10); // num is now 123
```

- Using Unary Plus Operator (+):

```
let str = "123";
let num = +str; // num is now 123
```

# Converting a Number to a String :

- Using the String Constructor:

```
let num = 123;
let str = String(num); // str is now "123"
```

- Using the toString Method:

```
let num = 123;
let str = num.toString(); // str is now "123"
```

- String Template Literals:

```
let num = 123;
let str = `${num}`; // str is now "123"
```

- String Concatenation:

```
let num = 123;
let str = num + ""; // str is now "123"
```

# typeof operator :

The typeof operator in JavaScript is used to determine the type of a variable or expression. It returns a string indicating the type of the operand.

```
console.log(typeof true);            // Output: "boolean"
console.log(typeof undefined);       // Output: "undefined"
console.log(typeof null);            // Output: "object" (historical bug)
const arr = [1,2,3,4];
console.log(typeof arr)              //object
```

# Arrays:

Array is a data structure that stores a list of elements. These elements can be of any data type (such as numbers, strings, objects, or even other arrays). Arrays in JavaScript are indexed starting from zero and allow you to store and manipulate multiple values in a single variable.

# Functions:

A function is a block of code that performs a specific task or calculates a value. Functions are reusable pieces of code that can be defined once and called (executed) multiple times.

- To use function we need to invoke it.
- It's good to use a function with parameters instead of creating a new function when you want to reuse the same block of code to do similar tasks but with different inputs.
- All the functions are returning undefined by default.
- Any code which is written after the return statement will be ignored by JS.
```
function hello(){
  return "Hello World";
  console.log("Something") //ignored
  console.log("Something") //ignored
}
```

# Difference Between Parameter and Argument

Parameters are local variables or placeholders that can be used only in the function body not outside

- The value we pass while declaring a function is --> Parameter
- The value we pass while invoking a function is --> Argument

# Difference Between Function Definition and Function Expression :
- function keyword followed by the function name and a block of code.
- Can be declared anywhere in the code (hoisted), meaning you can call the function before its definition in the code.

```
function hello(){
  //some code here...
}
```
- Defined by assigning a function to a variable using either the function keyword or the arrow (=>) syntax.
- Must be defined before they are called; otherwise, you'll get an error.

Example using function keyword: 
```
const greet = function(){
  //some code here...
}
```
Example using arrow function (ES6):
```
const greet = () => {
  //some code here...
}
```