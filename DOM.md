# DOM (Document Object Model):
The DOM (Document Object Model) is an essential concept that represents the structure of an HTML or XML document as a tree of objects. The DOM provides a way to interact with and manipulate the content, structure, and style of web documents dynamically through JavaScript.

# Common DOM Manipulations :
- Select the element which returns a node object.
- Decide the effect we want to apply on the selected element.


# Window Object 
The window object is the global object provided by the browser that represents the browser's window. It serves as an interface to the browser's API, allowing us to access and manipulate various browser features and functionalities.

**note :** In JavaScript, many global functions and properties are available directly without needing to reference the window object explicitly. For instance, methods like alert(), console.log(), and setTimeout() are globally accessible. This is because these functions are properties of the window object, and when you use them without specifying window, JavaScript implicitly searches for them in the global context

# Document Object :
The `document` object in JavaScript represents the entire HTML or XML document and serves as the entry point to access and manipulate the DOM (Document Object Model). It is part of the global window object and provides various properties and methods to interact with the document's structure and content.

# `console.dir` Method
The `console.dir` method is used to display an interactive listing of the properties of a specified JavaScript object. It is useful for inspecting the properties and methods of objects.
```
console.dir(document);
```

# Element Selection :
- **getElementById :** 
Selects a single element by its unique ID. This method returns the element with the specified ID or null if no such element exists.
```
var element = document.getElementById('myElement');
```
- **getElementsByTagName :**
Selects all elements with a specific tag name. This method returns a live HTMLCollection of all elements that has index and length with the.

  **note :**
  We can't use array methods on an HTMLCollection, instead we should change it to an array first.
```
var elements = document.getElementsByTagName('p');
```

- **getElementsByClassName :**
Selects all elements with a specific class name. This method returns a live HTMLCollection (an array-like object) of all elements with the specified class name.
```
var elements = document.getElementsByClassName('myClass');
```

- **querySelector :**
Selects the first element that matches the specified CSS selector. If no elements match, it returns null.
**note :**If we use document.querySelector for selecting a list of items  it is just selecting the first item.
```
Syntax :

querySelector('any css selector')

document.querySelector('#id');
document.querySelector('.class_name');
document.querySelector('li:last-child')
```

- **querySelectorAll :**
elects all elements that match the specified CSS selector. This method returns a static NodeList (another array-like object) of all matching elements. we can run all array methods on it.
```
const allLi = document.querySelectorAll('.li');
allLi.forEach((item)=>{
  item.style.color = "blue"
});
```
**note :**
If we need the selected value many times it is better to assign it to a variable.
```
const element = document.getElementById('element');

element.style.backgroundColor = 'lightblue'; 
element.style.fontSize = '24px';
```

- **children and childNodes :**
  - `element.childNodes` : Returns a live NodeList of all child nodes, including text and comment nodes.
  - `element.children` : Returns a live HTMLCollection of the element's child elements (without text and comment nodes).
```
let parent = document.getElementById('parent');

parent.children;
parent.childNodes;

```

- **firstChild and lastChild :**

  - firstChild : Returns the first child node of the specified element. This includes all types of nodes, such as text nodes, comment nodes, and element nodes. It can return null if the element has no child nodes.

  - lastChild :  Returns the last child node of the specified element. Similar to firstChild, this includes all types of nodes and can return null if there are no child nodes.
```
const parent = document.getElementById('parentElement');

parent.firstChild;
parent.lastChild;
```

- **parentElement :**
Accesses the parent element of a given element. `parentElement` specifically returns the element node.
```
const child = document.querySelector('.child');
console.log(child.parentElement.parentElement.parentElement) //if we run out of nodes it is returning null
```

- **nextSibling , previousSibling :**
  - nextSibling : Returns the next sibling node of the specified element. The sibling node could be any type of node, including text nodes, comment nodes, and element nodes. It returns null if there is no next sibling.

  - Returns the previous sibling node of the specified element. Like nextSibling, it can be any type of node and returns null if there is no previous sibling.
```
const element = document.getElementById('myElement');

const next = child.nextSibling.nextSibling;
const previous = element.previousSibling;
```

- **previousElementSibling and nextElementSibling :**
Selects the previous or next sibling element of the given element. These only return element nodes (without text and comment nodes).
```
const child = document.querySelector('.child');

console.log(child.nextElementSibling);
console.log(child.previousElementSibling);
```

# Manipulating the text inside a DOM node :

- **textContent :**
The textContent property is used to get or set the text content of an element. It represents the content as plain text, without any HTML tags.
```
const div = document.querySelector('.div');

console.log(div.textContent); //Allowed
div.textContent = "I am a new text for heading"; //Allowed

div.textContent = `<p class="para">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa, beatae.</p>`; //Not Allowed
```

- **innerHTML :**
The innerHTML property is used to get or set the HTML content of an element. It includes the HTML tags and allows for the inclusion of HTML elements within the content.
```
const div = document.createElement('div');
div.innerHTML = "I am a text with innerHTML"; //Allowed
div.innerHTML = `<p class="para">Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa, beatae.</p>`; //Allowed

```

- **innerText :**
The innerText property in JavaScript is used to get or set the text content of an HTML element. It represents the visible text of an element, excluding any HTML tags or elements. Unlike innerHTML, which includes HTML markup, innerText only deals with plain text.
```
const smallHeading = document.createElement('h5');
smallHeading.innerText = "I am small heading";
```

- **nodeValue :** 
Retrieves or sets the value of a text node. This is a property of the Text node type and is not available on elements directly. To use nodeValue, you first need to access a Text node within an element.
```
const heading = document.querySelector('h1');

console.log(heading.firstChild.nodeValue)

Or :
console.log(heading.childNodes[0].nodeValue) //childNodes is returning a NodeList and having (index 0 : text) and length then the (text) property is having the nodeValue porperty which the text is stored in it.

```

# getAttribute
The getAttribute method retrieves the value of a specified attribute from an element. If the attribute is not present, it returns null.
```
const element = document.querySelector('#special');

console.log(element.getAttribute('id'));
console.log(element.getAttribute('class'));
console.log(element.getAttribute('href'));
console.log(element.getAttribute('alt'));
```

# setAttribute
The setAttribute method sets the value of a specified attribute on an element. If the attribute does not exist, it will be created. If the attribute already exists, its value will be updated.
```
Syntax:
element.setAttribute(attributeName, value);

var link = document.getElementById("myLink");

link.setAttribute("class", "myLink");
link.setAttribute("href", "https://newexample.com");
link.setAttribute("title", "New Example Site");
```

# className :
Allows us to check a class name, change the class name or add a class name.
```
// Check for className :
const element = document.querySelector('.heading');
console.log(element.className); //Showing all the class names that the element is having 

// Adding new className :
const image = document.querySelector('img');
image.className = "pic";
image.className = "bold"; //className is overriding the previous classes but we can write the class names together like this:
image.className = "bold pic" 
```

# classList :
The classList property provides a more convenient way to work with class names. It returns a DOMTokenList object that represents the list of classes. This object has several useful methods for adding, removing, and toggling classes.
```
// Add new class using ClassName :
image.classList.add('colored')
image.classList.add('text')

// shorter way for adding classes:
image.classList.add('colored', 'text', 'anything')

// Removes one or more class names:
image.classList.remove('anything')

// Checks if the element has the specified class name:
image.classList.contains('colored');

// Adds the class if it's not present, or removes it if it is :
image.classList.toggle("active");
```

# createElement
The createElement method is used to create a new HTML element. You pass the tag name of the element you want to create as a string.
```
Syntax:
var newElement = document.createElement(tagName);

var newDiv = document.createElement("div");
```

# createTextNode :
The createTextNode method creates a new text node. Text nodes are used to hold text content within an element.
```
Syntax:
var newTextNode = document.createTextNode(text);

var textNode = document.createTextNode("Hello, World!");
```

# Adding Dynamic Elements to DOM :
- **appendChild :**
The appendChild method adds a node as the last child of a specified parent node. You can use it to add elements or text nodes to the DOM.
```
const element = document.createElement('div');
const text = document.createTextNode('I am a simple Div');

element.appendChild(text);
document.body.appendChild(element);
```

- **insertBefore(newNode, referenceNode):** This method inserts a new node before a specified reference node within a parent node.
```
var newDiv = document.createElement("div");
var referenceDiv = document.getElementById("referenceDiv");
var parentDiv = document.getElementById("parentDiv");

parentDiv.insertBefore(newDiv, referenceDiv);
```


# replaceChild(newChild, oldChild)
This method replaces an existing child node with a new node.
```
Syntax:
parentNode.replaceChild(newChild, oldChild);

var newDiv = document.createElement("div");
var oldDiv = document.getElementById("oldDiv");
var parentDiv = document.getElementById("parentDiv");

parentDiv.replaceChild(newDiv, oldDiv);
```

# append() and prepend():
These methods add one or more nodes or strings to the end or the beginning of an element's child list, respectively.
```
Syntax:
element.append(newChild1, newChild2, ...);
element.prepend(newChild1, newChild2, ...);

var container = document.getElementById("container");
var newDiv = document.createElement("div");

container.append(newDiv); // Adds to the end
// or
container.prepend(newDiv); // Adds to the beginning
```

# .remove()
The .remove() method is a modern, straightforward way to remove an element from the DOM. It directly removes the element on which it is called.
```
  var div = document.getElementById("myDiv");
  div.remove(); // Removes the div from the DOM
```

# .removeChild():
The .removeChild() method is a more traditional approach for removing elements. It is used on a parent node to remove a specified child node.
```
Syntax:
parentElement.removeChild(childElement);

var parentDiv = document.getElementById("parentDiv");
var childDiv = parentDiv.getElementById("childDiv");
parentDiv.removeChild(childDiv); // Removes the childDiv from parentDiv
```

# Change CSS with style property:
In JavaScript, you can dynamically change the CSS styles of an element using the style property of the DOM element. The style property allows you to get or set inline CSS styles directly from JavaScript.
```
Syntax:
element.style.propertyName = "value";

div.style.backgroundColor = "lightgreen";
div.style.fontSize = "20px";
div.style.border = "2px solid black";
```

# Events :
Events in JavaScript are actions or occurrences that happen in the web browser, such as a user clicking a button, a page loading, or a form being submitted. JavaScript allows you to handle these events to make web pages interactive and responsive.

# Adding Event Listeners:
The addEventListener method allows you to attach an event handler to an element.

1. Select The Element you want to add event on.
2. run addEvenListener(what event, what to do or callback)

**note :** the callback function can be anonymos or it can be a reference. in refernce we should not invoke the function just only reference it.
```
// Anonymous Function:
const heading = document.querySelector('.heading');
heading.addEventListener('click', function(){
  console.log("Hello")
})


// Reference:
const heading = document.querySelector('.heading');
function hello(){
  console.log("Hello")
}
heading.addEventListener('click', hello);
```


# Mouse Events :
- click : means that the whole down and up action should be completed.
- mousedown : when the mouse is pressed
- mouseup : when the mouse is released 
- mouseenter : when we move onto an element
- mouseleave : when we go out of an element
```
const heading = document.querySelector('.heading');
heading.addEventListener('click', function(){
  console.log("Click!!!!!!")
})

heading.addEventListener('mousedown', function(){
  console.log("Down!!!!!!")
})

heading.addEventListener('mouseup', function(){
  console.log("Up!!!!!!")
})

heading.addEventListener('mouseenter', function(){
  heading.classList.add('red')
})

heading.addEventListener('mouseleave', function(){
  heading.classList.remove('red')
})

```


# Key Events:
- keydown : Fired when a key is pressed down.
- keyup : Fired when a key is released.
- keypress : Fired when a key is pressed down and a character is generated. 
```
const input = document.querySelector('#input');

input.addEventListener('keypress', function(){
  console.log("Dowm Key!!!!!");
})

input.addEventListener('keyup', function(){
  console.log("You pressed Key!!!!!");
  console.log(input.value);
})

input.addEventListener('keydown', function(){
  console.log("Up Key!!!!!");
})

```

# Event Object :
It contains information about the event that occurred and provides methods to control the event's behavior.
It is giving us all the info about the triggered object.

### Properties and methods of the Event Object:
- **type:** The type of the event (e.g., "click", "keydown", "submit").
```
const heading = document.querySelector('.heading');

heading.addEventListener('click', (eve)=>{
  console.log(eve.type) //click
});
```

- **currentTarget:** The element that the event is attached to that.
```
const input = document.querySelector('#input');

input.addEventListener('keydown', function(e){
  console.log(e.currentTarget); //e.currentTarget will be input
});
```

- **target:** The element that triggered the event. This is the actual element that was clicked, typed on, or otherwise interacted with by the user.
```
const heading = document.querySelector('.heading');

heading.addEventListener('click', (eve)=>{
  console.log(eve.target);
});
```

- **preventDefault() :** Prevents the default action associated with the event (e.g., preventing form submission or following a link).
```
const link = document.querySelector('#link');

link.addEventListener('click', function(e){
  e.preventDefault();
});
```

# `target` vs `currentTarget` :
`currentTarget` is refering to the element to which the event listener has been attached.
`target` is refering to the element that the event happens on it.
```
html:
<button id="outerButton">
  Outer Button
  <strong id="innerButton">
    Nested Text
  </strong>
</button>


js:
const outerButton = document.querySelector('#outerButton');

outerButton.addEventListener('click', function(e){
  console.log('Target : ', e.target);
  console.log('Current Target : ', e.currentTarget);
});
```


# Using this keyword in Event Object :
Whe can select an element by this keyword as well. If we used an arrow function this will return window obj but if we used function expression it will return the element which has the eventListener.
```
const heading = document.querySelector('.heading');

heading.addEventListener('click', function(){
  console.log(this); // returning heading
})
```


# Event Propagation
In JavaScript, when an event occurs (like a click or a keypress), it doesn't just affect the element that directly receives the event. Instead, the event propagates through a hierarchy of elements. This is known as event propagation, and it happens in two phases:

- Capturing Phase: The event starts from the top of the document and travels down to the target element. This is the "capture" phase.
```
html:
<div class="container">
    <ul class="list">
        <li class="item"><a href="#">Link</a></li>
        <li class="item"><a href="#">Link</a></li>
    </ul>
</div>



js:
const list = document.querySelector('.list');
const container = document.querySelector('.container');

window.addEventListener('click', (e) => {
  console.log("Target : ", e.target);
  console.log("Current Target : ", e.currentTarget);
}, { capture: true }); // Capturing phase

document.addEventListener('click', (e) => {
  console.log("Target : ", e.target);
  console.log("Current Target : ", e.currentTarget);
}, { capture: true }); // Capturing phase

container.addEventListener('click', (e) => {
  console.log("Target : ", e.target);
  console.log("Current Target : ", e.currentTarget);
}, { capture: true }); // Capturing phase

list.addEventListener('click', (e) => {
  console.log("Target : ", e.target);
  console.log("Current Target : ", e.currentTarget);
}, { capture: true }); // Capturing phase



output:
Target : <a>
Current Target : window

Target : <a>
Current Target : document

Target : <a>
Current Target : .container

Target : <a>
Current Target : .list
```


- Bubbling Phase: After reaching the target element, the event bubbles back up to the top, passing through each parent element. This is the "bubble" phase.
```
html:
  <div class="container">
    <ul class="list">
      <li class="item"><a href="#">Link</a></li>
      <li class="item"><a href="#">Link</a></li>
    </ul>
  </div>


js:
const list = document.querySelector('.list');
const container = document.querySelector('.container');

list.addEventListener('click', (e) => {
  console.log("Target : ", e.target);
  console.log("Current Target : ", e.currentTarget);
});

container.addEventListener('click', (e) => {
  console.log("Target : ", e.target);
  console.log("Current Target : ", e.currentTarget);
});

document.addEventListener('click', (e) => {
  console.log("Target : ", e.target);
  console.log("Current Target : ", e.currentTarget);
});

window.addEventListener('click', (e) => {
  console.log("Target : ", e.target);
  console.log("Current Target : ", e.currentTarget);
});



output:
Target : <a>
Current Target : .list

Target : <a>
Current Target : .container

Target : <a>
Current Target : document

Target : <a>
Current Target : window
```

**note :** We can stop the propagation using `e.stopPropagation()`.

```
const list = document.querySelector('.list');
const container = document.querySelector('.container');
list.addEventListener('click', (e)=>{
  console.log("Target : ",e.target);
  console.log("Current Target : ",e.currentTarget);
});

container.addEventListener('click', (e)=>{
  console.log("Target : ",e.target);
  console.log("Current Target : ",e.currentTarget);
  e.stopPropagation(); //e.stopPropagation() prevents any further bubbling past the container, so no further logs appear from document or window in the bubbling phase.
});

document.addEventListener('click', (e)=>{
  console.log("Target : ",e.target);
  console.log("Current Target : ",e.currentTarget);
});

window.addEventListener('click', (e)=>{
  console.log("Target : ",e.target);
  console.log("Current Target : ",e.currentTarget);
});

output:
Target : <a>
Current Target : .list

Target : <a>
Current Target : .container
```


# Propagation Example:
```
html:
  <div class="container">
    <h1 class="heading">I am inside the container!</h1>
  </div>
  <button class="btn">Add Element</button>

js:

If we add h1 in HTML we can acces it in JS:
const heading = document.querySelector('.heading');
const container = document.querySelector('.container');
const btn = document.querySelector('.btn');


Event for the heading that is added using html:
heading.addEventListener('click', function(){
  console.log("Hello there !!!!!!!!");
});



If we remove the h1 from HTML and add h1's using JS it is showing error because we can't access dynamic element using querySelector.
btn.addEventListener('click', function(){
  const element = document.createElement('h1');
  element.classList.add('heading');
  element.textContent = `I am inside the container!`;
  container.appendChild(element);
});


That is why we have to add the event listener to the parent of h1's so using bubbling by clicking on h1's the event of their parents will fire up.
container.addEventListener('click', function(e){
  if(e.target.classList.contains('heading')){
    console.log("Hello there !!!!!!!!")
  }
});
```

# Form Events (submit)
```
html:
<form action="" id="form">
  <input type="text" name="name" id="name">
  <input type="password" name="password" id="password">
  <input type="submit" value="submit" id="submit">
</form>


js:
const form = document.querySelector('#form');
const name = document.querySelector('#name');
const password = document.querySelector('#password');

form.addEventListener('submit', function(e){
  e.preventDefault();
  console.log("Form submitted!!!!");
  console.log(name.value);
  console.log(password.value);
});
```

# Web Storage API (Local Storage and Session Storage)
- **Local Storage :** Data stored in local storage persists across browser sessions. This means that the data will remain even if the browser is closed and reopened. Local storage data is shared across all tabs and windows within the same origin (protocol, domain, and port).
```
/ Store data
localStorage.setItem('username', 'JohnDoe');

// Retrieve data
const username = localStorage.getItem('username');

// Remove data
localStorage.removeItem('username');

// Clear all local storage
localStorage.clear();
```
- **Session Storage :** Data stored in session storage is only available for the duration of the page session. A page session lasts as long as the browser is open, and survives page reloads and restores. However, it is cleared when the page session ends, which usually happens when the browser or tab is closed. Session storage is limited to the specific tab or window. Data stored in session storage is not shared between tabs or windows, even if they are for the same origin.
```
// Store data
sessionStorage.setItem('sessionKey', 'sessionValue');

// Retrieve data
const sessionValue = sessionStorage.getItem('sessionKey');

// Remove data
sessionStorage.removeItem('sessionKey');

// Clear all session storage
sessionStorage.clear();
```

# Storing multiple values in local Storage:
- Convert the Array or Object to a JSON String: Use `JSON.stringify()`
- Convert the String Back to an Array or Object: Use `JSON.parse()`
```
const fruits = ['Apple', "Peach", "Mango"];
localStorage.setItem('fruits', JSON.stringify(fruits));
console.log(JSON.parse(localStorage.getItem('fruits'))[0]);
```

# `setTimeout()`:
It runs a function once after a specific time.

**Syntax of setTimeout :**
```
setTimeout(function, delay, arg1, arg2, ...);
```
- function: The function to execute after the delay.
- delay: The time (in milliseconds) to wait before executing the function.
- arg1, arg2, ... (optional): Additional arguments to pass to the function when it executes.

```
Example Without Arguments:

// Function to be executed
function greet() {
    console.log('Hello after 2 seconds!');
}

// Set the timeout
const timeoutId = setTimeout(greet, 2000); //function reference no invoking.
```
```
Example With Arguments:
// Function to be executed with arguments
function greet(name, age) {
    console.log(`Hello ${name}, you are ${age} years old.`);
}

// Set the timeout with arguments
const timeoutId = setTimeout(greet, 2000, 'Alice', 30);
```

### Clearing the Timeout :
You can use clearTimeout to cancel a timeout that has been set but not yet executed.

### `setTimeout()` unique identifier:
In js setTimeout returns a unique identifier which is a value that you can use to manage the timeout. This identifier is crucial for canceling the timeout before it executes, if necessary.

```
// Function to be executed
function greet() {
    console.log('This will not be shown.');
}

// Set the timeout and get the timeout ID
const timeoutId = setTimeout(greet, 2000);

// Clear the timeout before it executes
clearTimeout(timeoutId);
```

# `setInterval()` :
setInterval in JavaScript is a function used to repeatedly execute a given function at specified intervals.

**Syntax of setInterval:**
```
setInterval(function, interval, arg1, arg2, ...);
```

```
Example without argument:

// Function to be executed
function logMessage() {
    console.log('This message is logged every second.');
}

// Set the interval to call `logMessage` every 1000 milliseconds (1 second)
const intervalId = setInterval(logMessage, 1000);


Example with argument:
// Function to be executed with arguments
function greet(name, time) {
    console.log(`Hello ${name}, it's ${time} now.`);
}

// Set the interval to call `greet` every 2000 milliseconds (2 seconds)
const intervalId = setInterval(greet, 2000, 'Alice', new Date().toLocaleTimeString());
```

# Clearing the Interval:
To stop the repeated execution, use `clearInterval` with the unique identifier returned by `setInterval`.
```
function greet(name, time) {
    console.log(`Hello ${name}, it's ${time} now.`);
}

const intervalId = setInterval(greet, 2000, 'Alice', new Date().toLocaleTimeString());

clearInterval(intervalId);
```

# DOMContentLoaded :
The DOMContentLoaded event in JavaScript is an important event that indicates when the initial HTML document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading. This event is useful when you want to execute JavaScript code as soon as the DOM (Document Object Model) is ready, but before the whole page (including images and stylesheets) has finished loading.
```
document.addEventListener('DOMContentLoaded', function() {
    console.log('The DOM is fully loaded and parsed.');
});
```

# `DOMContentLoaded` Vs `window.onload`
- `DOMContentLoaded`: Fires when the DOM is fully loaded and parsed.
- `load`: Fires when a resource and its dependent resources have been fully loaded. This can include the entire page with all its assets (images, stylesheets, scripts, etc.), or it can apply to individual resources.
```
// Example using load event
window.addEventListener('load', function() {
    console.log('The entire page, including all resources, is fully loaded.');
});
```

# `scroll` Event:
The scroll event in JavaScript is triggered when an element or the entire window is scrolled. 
- scrollY: This property returns the number of pixels that the document has already been scrolled vertically from the top.
- scrollX: This property returns the number of pixels that the document has already been scrolled horizontally from the left.

Syntax:
```
element.addEventListener('scroll', function(event) {
    // Code to run when the element is scrolled
});
```

Scrolling the Window :
```
window.addEventListener('scroll', function() {
    console.log('The window is scrolled.');
    console.log('Scroll position:', window.scrollY); // Vertical scroll position
});
```

# `window.innerHeight` :
Returns the height of the viewport (the visible part of the browser window) in pixels.
```
console.log('Viewport height:', window.innerHeight);
```

# `window.innerWidth` :
Returns the width of the viewport in pixels.
```
console.log('Viewport width:', window.innerWidth);
```

# `getBoundingClientRect()` :
A method of an HTML element that returns a DOMRect object providing information about the size and position of the element relative to the viewport. It includes properties like top, right, bottom, left, width, and height.
```
css:
<style>
  #myElement {
      width: 200px;
      height: 100px;
      background-color: lightblue;
      margin-top: 500px; /* To demonstrate scrolling */
  }
</style>

html:
<div id="myElement">
  Hello, I'm an element!
</div>

js:
function logElementRect() {
          const rect = element.getBoundingClientRect();
          console.log('Element position and size:', rect);
          console.log('Top:', rect.top);
          console.log('Right:', rect.right);
          console.log('Bottom:', rect.bottom);
          console.log('Left:', rect.left);
          console.log('Width:', rect.width);
          console.log('Height:', rect.height);
      }

logElementRect();
```

# `resize` Event:
The resize event in JavaScript is triggered when the size of the viewport or an element is changed. 
```
window.addEventListener('resize', function() {
    console.log('Window resized.');
    console.log('New viewport width:', window.innerWidth);
    console.log('New viewport height:', window.innerHeight);
});
```