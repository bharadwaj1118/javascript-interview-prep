# DOM Manipulation Methods Study Notes

## 1. ELEMENT SELECTION & TRAVERSAL
------------------------------------------------------------------------------
### Document Methods:
- `getElementById(id)` → Returns a single element with the specified ID attribute
- `getElementsByClassName(className)` → Returns a live HTMLCollection of elements with the specified class name
- `getElementsByTagName(tagName)` → Returns a live HTMLCollection of elements with the specified tag name
- `querySelector(selector)` → Returns the first element that matches the specified CSS selector
- `querySelectorAll(selector)` → Returns a static NodeList of all elements matching the specified CSS selector

### Element Traversal:
- `parentNode` / `parentElement` → Returns the parent node/element of the specified node
- `children` / `childNodes` → Returns a HTMLCollection/NodeList of child elements/nodes
- `firstChild` / `firstElementChild` → Returns the first child node/element of the specified node
- `lastChild` / `lastElementChild` → Returns the last child node/element of the specified node
- `nextSibling` / `nextElementSibling` → Returns the next sibling node/element
- `previousSibling` / `previousElementSibling` → Returns the previous sibling node/element
- `contains(element)` → Returns true if a node is a descendant of the specified node

## 2. ELEMENT CREATION & MODIFICATION
------------------------------------------------------------------------------
### Creating Elements:
- `document.createElement(tagName)` → Creates a new element with the specified tag name
- `document.createTextNode(text)` → Creates a new text node with the specified text
- `document.createDocumentFragment()` → Creates an empty DocumentFragment for efficient DOM operations
- `element.cloneNode(deep)` → Creates a copy of a node; deep=true includes all descendants

### Adding & Removing Elements:
- `appendChild(node)` → Adds a node as the last child of a node
- `insertBefore(newNode, referenceNode)` → Inserts a node before a reference node as a child of a specified parent node
- `replaceChild(newNode, oldNode)` → Replaces a child node with a new node
- `removeChild(node)` → Removes a child node from the DOM
- `remove()` → Removes the element from the DOM
- `insertAdjacentElement(position, element)` → Inserts an element at a specified position ('beforebegin', 'afterbegin', 'beforeend', 'afterend')
- `prepend()` / `append()` → Inserts nodes or text at the beginning/end of an element
- `before()` / `after()` → Inserts nodes or text before/after an element in its parent's children list

## 3. ATTRIBUTE MANIPULATION
------------------------------------------------------------------------------
### Attribute Methods:
- `getAttribute(name)` → Returns the value of the specified attribute
- `setAttribute(name, value)` → Sets or changes the value of the specified attribute
- `removeAttribute(name)` → Removes the specified attribute from an element
- `hasAttribute(name)` → Returns true if the element has the specified attribute
- `toggleAttribute(name, force)` → Toggles the specified boolean attribute (adds if absent, removes if present)

### Class Manipulation:
- `classList.add(className)` → Adds one or more class names to an element
- `classList.remove(className)` → Removes one or more class names from an element
- `classList.toggle(className)` → Toggles a class name (adds if absent, removes if present)
- `classList.contains(className)` → Returns true if the element has the specified class
- `classList.replace(oldClass, newClass)` → Replaces an existing class with a new class

### Data Attributes:
- `dataset` → Provides read/write access to all the custom data attributes (data-*) on an element
- `dataset.propertyName` → Accesses a specific data attribute (data-property-name becomes dataset.propertyName)

## 4. STYLE MANIPULATION
------------------------------------------------------------------------------
- `style.propertyName` → Gets/sets a specific CSS property of an element (camelCase: e.g., backgroundColor)
- `style[propertyName]` → Alternative way to get/set a CSS property using bracket notation
- `style.setProperty(name, value, priority)` → Sets a CSS property with optional priority ("important")
- `style.removeProperty(name)` → Removes a CSS property from an element
- `style.cssText` → Gets/sets all inline CSS properties as a string
- `getComputedStyle(element)` → Returns an object containing the computed style values for an element

## 5. CONTENT MANIPULATION
------------------------------------------------------------------------------
- `innerHTML` → Gets/sets the HTML content inside an element
- `outerHTML` → Gets/sets the HTML of an element including its content and the element itself
- `textContent` → Gets/sets the text content of a node and its descendants
- `innerText` → Gets/sets the visible text content of a node (respects CSS styling)
- `insertAdjacentHTML(position, text)` → Inserts HTML at a specified position relative to the element

## 6. EVENT HANDLING
------------------------------------------------------------------------------
- `addEventListener(event, handler, options)` → Attaches an event handler function to an element
- `removeEventListener(event, handler, options)` → Removes an event handler previously attached with addEventListener
- `dispatchEvent(event)` → Triggers an event on an element
- `preventDefault()` → Cancels the default action that belongs to the event
- `stopPropagation()` → Prevents an event from bubbling up the DOM tree
- `stopImmediatePropagation()` → Prevents other listeners of the same event from being called

## 7. FORM MANIPULATION
------------------------------------------------------------------------------
- `form.submit()` → Submits a form programmatically
- `form.reset()` → Resets a form to its initial values
- `form.elements` → Returns a collection of all form control elements
- `form.checkValidity()` → Returns true if the form's elements all validate
- `input.focus()` / `input.blur()` → Gives/removes focus from an input element
- `input.select()` → Selects all the text in a text field
- `input.value` → Gets/sets the value of an input element
- `input.checked` → Gets/sets the checked state of a checkbox or radio button

## 8. DIMENSIONS & POSITION
------------------------------------------------------------------------------
- `getBoundingClientRect()` → Returns the size and position of an element relative to the viewport
- `offsetWidth` / `offsetHeight` → Returns the visible width/height of an element including borders and padding
- `clientWidth` / `clientHeight` → Returns the visible width/height of an element excluding borders
- `scrollWidth` / `scrollHeight` → Returns the entire width/height of an element, including parts hidden by overflow
- `offsetLeft` / `offsetTop` → Returns the distance from the element's left/top edge to its offset parent's left/top edge
- `scrollLeft` / `scrollTop` → Gets/sets the number of pixels that an element's content is scrolled horizontally/vertically
- `scrollIntoView(options)` → Scrolls the element into the visible area of the browser window

## 9. NODE PROPERTIES
------------------------------------------------------------------------------
- `nodeType` → Returns the type of node (1=element, 3=text, 8=comment, 9=document)
- `nodeName` → Returns the name of a node (tag name for elements, #text for text nodes)
- `nodeValue` → Gets/sets the value of a node (text for text nodes, null for elements)
- `tagName` → Returns the tag name of an element in uppercase
- `id` → Gets/sets the id attribute of an element
- `className` → Gets/sets the class attribute of an element (as a space-separated string)
- `hidden` → Gets/sets whether an element is hidden (equivalent to display: none)
- `tabIndex` → Gets/sets the tab order of an element

## NOTES & EXAMPLES:
------------------------------------------------------------------------------
```javascript
// Quick examples:

// Selection
const element = document.getElementById('myId');
const buttons = document.querySelectorAll('button.primary');

// Creation and adding
const newDiv = document.createElement('div');
newDiv.textContent = 'New content';
document.body.appendChild(newDiv);

// Attributes and classes
element.setAttribute('data-role', 'navigation');
element.classList.add('active');

// Styles
element.style.backgroundColor = 'lightblue';
element.style.setProperty('margin', '10px', 'important');

// Content
element.innerHTML = '<span>Updated content</span>';
element.textContent = 'Plain text only';

// Events
element.addEventListener('click', () => alert('Clicked!'));

// Position
const rect = element.getBoundingClientRect();
console.log(`Element is at coordinates (${rect.left}, ${rect.top})`);
```
