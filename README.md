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

```
const everything = ['a', "apple", 30, [1,3,5], true]
```

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

- The value we pass while declaring a function is Parameter.
- The value we pass while invoking a function is Argument.

```
funtion hello(name){ // name is parameter
  console.log("Hello I am " + name);
}

hello("Susan") // Susan is argument

```


# Difference Between Function Declaration and Function Expression :

- The `function` keyword followed by the function name and a block of code is called Function Declaration.
- Can be declared anywhere in the code (hoisted), meaning you can call the function before its definition in the code.

```
function hello(){
  //some code here...
}
```

- Assigning a function to a variable using either the function keyword or the arrow (=>) syntax is called function expression.
- Must be defined before they are called; otherwise, you'll get an error.


```
const greet = function(){
  //some code here...
}

or 

const greet = () => {
  //some code here...
}
```

# Objects:

An object is a fundamental data type that allows you to store collections of key-value pairs.

- If the property of an object was a function then it is called as method.
- For using the object properties or invoking the methods we can use :

  - dot notation.

  ```
  const person = {
    name: "Sana",
    greeting: function(){
      console.log("Hello my name is " + this.name);
    },
    greeting2(){ //ES6 Syntax for methods :
      console.log("Hey my name is " + this.name);
    }
  }

    console.log(person.name); //dot notation
    person.greeting(); //dot notation

  ```

  - Bracket Notation

  ```
  const person = {
    name: "Sana",
    greeting: function(){
      console.log("Hello my name is " + this.name);
    }
  }

    console.log(person["name"]); //bracket notation
    person['greeting']() //bracket notation
  ```

**Note** : 
Functions can accept parameters and the parameter can be even an object :
<br><br>
In the example even though the object's properties are passed in reverse order (lastName before firstName), the function correctly constructs the full name as "Peter Helen" and converts it to uppercase.
```
function Name({ firstName, lastName }) {
    let fullName = `${firstName} ${lastName}`;
    return fullName.toUpperCase();
}

console.log(Name({ lastName: "Helen", firstName: "Peter" })); 

Output : PETER HELEN
```


# Conditional Statements

Conditional statements in JavaScript are used to make decisions in your code based on certain conditions. They allow your program to execute different blocks of code depending on whether a condition is true or false.

- if Statement
- if...else Statement
- if...else if...else Statement
- Switch Statement
  <br><br>

# Comparison Operators :

- `>`, `<`
- `>=`, `<=`
- `!=`, `!==`
- `==`(checks only value), `===`(checks value and type)

# if(!value) and if(value)

In JS `if(!value)` means if the value was falsy it will run the if block and it will accept the `false` as an acceptable condition.
<br>
The `if(value)` means if the value was truthy then the if block will run.

In JavaScript, the following values are considered "falsy" and the rest are considered as truthy:

- `false` (boolean false)
- `0` and `-0` (number zero)
- `''` , `""` or (``) (empty strings)
- `null`
- `undefined`
- `NaN` (Not a Number)

```
As the value is an empty string JS will take it as a fals value and then the if block will be executed:

let value = "";
if(!value){
  console.log('If is running')
}else{
  console.log("Else is running")
}

Output : If is running
```

# Loops :

Loops in JavaScript are used to repeatedly execute a block of code as long as a specified condition is true.

- while loops : first checking if the condition was true then running the code block.

```
let amount = 10;
while(amount > 0){
  console.log("I am having "+ amount + "$");
  amount--;
}
```

- do while loops : It runs the code block one time and then checking if the condition was true.

```
let amount = 12;
do {
  console.log("You earned " + amount + " dollars");
  amount++;
} while (amount < 10);
```

- for loops : It executes the block of code as long as the condition is true.

```
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

# String methods :
```
let name = "  Sana Tameem ";

console.log(name); //   Sana Tameem 

console.log(name.length); //14

console.log(name.toLowerCase()); //  sana tameem

console.log(name.toUpperCase()); //  SANA TAMEEM

console.log(name.charAt(3)); //a

console.log(name.indexOf('T')); //7

console.log(name.trim()); //Sana Tameem

console.log(name.includes('eem')); //true

console.log(name.startsWith('  Sana')); //true

console.log(name.trim().toLowerCase().startsWith('sana')); //true

console.log(name.slice(0,3));//(  S) --> start from zero 3 not included

console.log(name.slice(-3)); //(em ) --> last three letters of the string
```

# Template Literals:
Template literals, introduced in ECMAScript 6 (ES6), are a way to create strings in JavaScript that allows for embedded expressions and multi-line strings. They are enclosed by backticks (``) instead of single quotes ('') or double quotes ("").

**Interpolation** :
 To insert an expression in backticks we use ${}
 ```
let name = 'John';
let age = 30;

let message = `Hello, my name is ${name} and I am ${age} years old.`;
 ```

# Array Mthods and properties:
**Properties : ** 
- length
- concat()
- reverse()
```
let arr = [1,2,3,4,5,6,7];
let arr2 = [8,9,0];

console.log(arr.length); //7

console.log(arr.concat(arr2)); //[1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

console.log(arr.reverse()); //[7, 6, 5, 4, 3, 2, 1]
```
**Methods : **
```
let arr = [1,2,3,4,5,6,7];
console.log(arr); // [1, 2, 3, 4, 5, 6, 7]

removedItem = arr.splice(2,2)//mutates the original array - first argument is from which index it should start, second value is saying how many items it should remove

console.log(removedItem); //[3, 4]
console.log(arr); //[ 1, 2, 5, 6, 7 ]

arr.unshift(12);//Adding at the first
console.log(arr); //[ 12, 1, 2, 5, 6, 7 ]

console.log(arr.shift()); //1 --> removing and returning the first value of array
console.log(arr); //[ 1, 2, 5, 6, 7 ]

arr.push(30); //adds to the end of array
console.log(arr) //[ 1, 2, 5, 6, 7, 30 ]

arr.pop(); //removes from the last
console.log(arr) //[ 1, 2, 5, 6, 7 ]
```

# Value vs Reference
- If we are assigning a primitiv data type value to another variable even if we change the value its original value will not be changed.
```
const number = 2;
let number2 = number;
number2 = 4;

console.log(`The first value is : ${number}`); //The first value is : 2
console.log(`The second value is : ${number2}`); //The second value is : 4
```

- If we are assigning a non-primitiv data type to another variable and we change the value; its original value will also be changed because it is changine the reference. 
```
const person = {name: "Sana"}
let person2 = person;
person2.name = "Anna";

console.log(`The first person is : ${person.name}`); // The first person is : Anna
console.log(`The second person is : ${person2.name}`); // The second person is : Anna
```

- The solution for the above problem is using the spread operator. Spread operator will not change the value of the reference.
```
const person3 = {name: "Sana"}
let person4 = {...person};
person4.name = "Susy";

console.log(`The first person is : ${person3.name}`); // The first person is : Sana
console.log(`The second person is : ${person4.name}`); // The second person is : Susy
```

# Undefined vs Null
- `undefined` represents a variable that has been declared but not initialized, or an object property that does not exist.
- `null` represents an intentional absence of any object value.
let num = 20 + null; 
console.log(num); //20
let num2 = 20 + undefined;
console.log(num2); //Nan

# Using return to Control Function Execution:

The return statement in JavaScript serves two primary purposes: 
<br><br>
- Specifies the value a function should return
- Acts as a mechanism to immediately stop the function's execution and exit.
```
let food = [56, 200, 1300];
let gas = [67,1,5];

function calculate(arr){
  let total = 0;
  for(let i = 0; i < arr.length; i++){
    total += arr[i];
  }
  if(total>100){
    console.log("Woa!!!!! You are spending too much");
    return total; // stops the function here only and the function well not print the next clg and next return;
  }
  console.log("You are good at spending");
  return total;
}

console.log(calculate(food)); //Woa!!!!! You are spending too much // 1556
console.log(calculate(gas)); //You are good at spending //73
console.log(calculate([20+40+500])); //Woa!!!!! You are spending too much //560
```

# Unary, Binary and Ternary Operators :
- Unary Operator : Unary operators work with one operand like `typeof`.
```
console.log(typeof "Sana");
```
- Binary Operator : Binary operators work with two operands like addition.
```
console.log(3 + 5)
```
- Ternary Operator: The ternary operator (?:) is the only ternary operator in JavaScript. It works with three operands and is used as a shorthand for if...else statements.
```
condition ? run if condition is true : run if condition is false

const value = 2>1;
value ? console.log("Truthy") : console.log("Falsy") //Truthy
```

