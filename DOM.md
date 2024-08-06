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
Retrieves or sets the text content of an element. It returns the text as a single string, including all text nodes within the element but excluding HTML tags. It also replaces any existing content with the new text if set.
```
const heading = document.querySelector('h1');

console.log(heading.textContent);
heading.textContent = "I am a new text for heading";
```

- **nodeValue :** 
Retrieves or sets the value of a text node. This is a property of the Text node type and is not available on elements directly. To use nodeValue, you first need to access a Text node within an element.
```
const heading = document.querySelector('h1');

console.log(heading.firstChild.nodeValue)

Or :
console.log(heading.childNodes[0].nodeValue) //childNodes is returning a NodeList and having (index 0 : text) and length then the (text) property is having the nodeValue porperty which the text is stored in it.

```