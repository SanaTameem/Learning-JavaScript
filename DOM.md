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
