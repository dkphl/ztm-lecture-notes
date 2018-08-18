# Lesson 105 - DOM Events
### links for this lesson
- [MDN Event Reference](https://developer.mozilla.org/en-US/docs/Web/Events)
- [Javascript Char Code Reference](https://www.cambiaresearch.com/articles/15/javascript-char-codes-key-codes)

## addEventListener
- takes two arguments:
    - the event to listen for, and
    - the function to run once the event occurs

```javascript
document.querySelector('h1').addEventListener('eventListener', function {
    // function to run upon event occurence
  });
```

## createElement
- creates HTML element with the specified tag name (div, h1, li, etc.)

```javascript
var element = document.createElement('tagName');
```

## appendChild
- adds a node to the end of a parent

```javascript
// Create a new list item element, and append it to the end of the unordered list parent
var li = document.createElement("li");
document.querySelector('ul').appendChild(li);
```

## event info
- the eventListener function automatically receives parameter that contains the info of the actual event

```javascript
addTodo.addEventListener('click', function (event) {   
  console.log(event);
});
// MouseEvent {isTrusted: true, screenX: 228, screenY: 268, clientX: 212, clientY: 136, …}
```

- using this, we can call functions based on the methods available in the event info, such as a specific keypress

```javascript
function addTodoAfterKeypress (event) {
  if (inputLength() > 0 && event.keyCode === 13) {
    addTodoItem();
  }
}
// keycode 13 corresponds to the enter key, so hitting the enter key records the new todo item

todoNameInput.addEventListener('keypress', addTodoAfterKeypress);
```

### resource: [Javascript Char Code Reference](https://www.cambiaresearch.com/articles/15/javascript-char-codes-key-codes)


## D.R.Y. Principles & refactoring
- avoid repeating code
- once you have working code, analyze it to see where it could be cleaned up (refactoring)
- remember to store functions in variables to avoid having to repeat them
    - make sure to use descriptive variable names

```javascript
// THIS IS MUCH CLEANER THAN WHERE THE CODE STARTED, WITH THE SAME FUNCTIONS BEING WRITTEN REPEATEDLY

let todoNameInput = document.getElementById('todoNameInput');
let addTodoButton = document.getElementById('addTodoButton');
let todoList = document.querySelector('ul');

function inputLength () {
 return todoNameInput.value.length; 
}

function addTodoItem () {
  let newItem = document.createElement('li');
  todoList.appendChild(newItem).textContent = todoNameInput.value;
  todoNameInput.value = '';
}

function addTodoAfterClick () {
  if (inputLength() > 0) {
    addTodoItem();
  }
}

function addTodoAfterKeypress (event) {
  if (inputLength() > 0 && event.keyCode === 13) {
    addTodoItem();
  }
}

addTodoButton.addEventListener('click', addTodoAfterClick);

todoNameInput.addEventListener('keypress', addTodoAfterKeypress);

```

### a note on callback functions:
- by default, you can't pass an argument to a callback function, hence why we must have this:
```javascript
addTodoButton.addEventListener('click', addTodoAfterClick);

todoNameInput.addEventListener('keypress', addTodoAfterKeypress);

```
- rather than this:
```javascript
addTodoButton.addEventListener('click', addTodoAfterClick());

todoNameInput.addEventListener('keypress', addTodoAfterKeypress(event));

```

