# Lesson 103 - DOM Selectors
<br>
## getElementsByTagName

returns an array of all elements matching the tag (h1, p, li, etc.)

```javascript
document.getElementsByTagName('tagName');
```
can also specify and index, to target a specific one:

```javascript
document.getElementsByTagName('tagName')[#];
```
<br>

## getElementsByClassName
returns an array of all elements matching the class name
```javascript
document.getElementsByClassName('className');
```
<br>
can also be targeted via an index number:
```javascript
document.getElementsByClassName('className')[#];
```
<br>
## getElementById
returns a single element matching the id
```javascript
document.getElementById('idName');
```<br>
## querySelector & querySelectorAll
- more powerful the getElementsBy
- can target many types of elements (class, id, h1, ul, li, etc.)
- if targeting class or id, must use prefix (i.e. #id or .class)
```javascript
document.querySelectorAll('.className'); 
document.querySelector('#idName');
document.querySelectorAll('h2');
```<br>

## getAttribute
returns the requested attribute of the first element that matches the query selector (example below, the class name of the first h1 element)
```javascript
document.querySelector('h1').getAttribute('class');
```
<br>
##setAttribute
- changes the given attribute for the chosen selector (id, class, other)
- takes two arguments - the attribute, and the attribute's new value

```javascript
document.querySelector('h1').setAttribute('id', 'idName');
```
<br>
# Changing Styles
style.{property} //ok

className //best
classList //best

classList.add
classList.remove
classList.toggle

# Bonus
innerHTML //DANGEROUS

parentElement
children

# It is important to CACHE selectors in variables
store selectors as variables - cleaner code, optimized web page
```javascript
let h1Class = document.querySelector('h1').getAttribute('class');
```