# Lesson 103 - DOM Selectors

## getElementsByTagName

returns an array of all elements matching the tag (h1, p, li, etc.)

```javascript
document.getElementsByTagName('tagName');
```
can also specify an index, to target a specific one:

```javascript
document.getElementsByTagName('tagName')[#];
```


## getElementsByClassName
returns an array of all elements matching the class name
```javascript
document.getElementsByClassName('className');
```

can also be targeted via an index number:
```javascript
document.getElementsByClassName('className')[#];
```

## getElementById
returns a single element matching the id
```javascript
document.getElementById('idName');
```

## querySelector & querySelectorAll
- more powerful the getElementsBy
- can target many types of elements (class, id, h1, ul, li, etc.)
- if targeting class or id, must use prefix (i.e. #id or .class)
```javascript
document.querySelectorAll('.className'); 
```
```javascript
document.querySelector('#idName');
```
```javascript
document.querySelectorAll('h2');
```

## getAttribute
returns the requested attribute of the first element that matches the query selector (example below, the class name of the first h1 element)
```javascript
document.querySelector('h1').getAttribute('class');
```

## setAttribute
- changes the given attribute for the chosen selector (id, class, other)
- takes two arguments - the attribute, and the attribute's new value

```javascript
document.querySelector('h1').setAttribute('id', 'idName');
```

# Changing Styles
```javascript
style.{property} //ok, but violates separation of concerns
```
## className
- add a class value to selected element
```javascript
document.querySelector('h1').className = 'title';
```
## classList
- returns a DOMTokenlist (array) of class attributes of the selected element
- available methods:
    - add, remove, toggle, replace, item, contains
```javascript
let h1 = document.querySelector('h1')

h1.classList;

h1.classList.add('class');

h1.classList.remove('class');

h1.classList.toggle('class'); // adds/removes, depending on if the class is present or not

h1.classList.replace('oldClass', 'newClass');

h1.classList.item(number); // to target a specific class in the list

h1.classList.contains('class'); // checks for existence of given class, returns boolean 

```
# Bonus
```javascript
innerHTML //DANGEROUS
```

```javascript
parentElement
children
```

# It is important to CACHE selectors in variables
store selectors as variables - cleaner code, optimized web page
```javascript
let h1Class = document.querySelector('h1').getAttribute('class');
```
```javascript
function selectElement (selector) {
  return document.querySelector(selector);
}
```
