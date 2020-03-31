# TIL for java script intern
***
## March 23  2020 / Fundamentals
---
#### Using console `console`

```javascript
console.log('Hello'); 
```
#### Single selector `getElementByID` , `querySelector`

```javascript
document.getElementById('idSelector');
document.querySelector('li').style.color = 'yellow';
document.querySelector('.select').style.color = "red";
document.querySelector('#select').style.color = "green"

```
#### Multiple selector `getElementByClassName` , `querySelectorAll` , `getElementByName` , `getElementByTagName`

#### Type conversion

| Method        | Description           |
| :------------- |:-------------| 
|   toString()     | Convert to string | 
| String(x)      | Convert number into String      |
| toFixed() | Fixed number rounded with given specific number |
| Number('text') | Convert text into number |
| Number(false/true) | Convert booleans to number 0/1 |

#### String Concatination `concat()`
```javascript
var str1 = "Hello ";
var str2 = "world!";
var res = str1.concat(str2);

string.concat(Hello, world!);
```
## March 24 2020 / DOM
---
#### Using `innerHTML` to add `text` in selector `id` and `style`
```javascript
const selector = document.getElementById('idSelector');
selector.innerHTML = 'Things i did today!';
selector.style.color = "skyblue";
```
#### Styling `li` items using `tag` , `class` , `id` selector
```javascript
document.querySelector('li').style.color = 'yellow';
document.querySelector('.select').style.color = "red";
document.querySelector('#select').style.color = "green"
```
## March 25 2020 / DOM
---
### DOM project - Task mamager
#### Functions of task manager
* add new task
* Remove individual task
* clear all task
* store in local storage

#### Appending child in parent tag with `appendChild`
```javascript
li.appendChild(document.createTextNode(taskInput.value));
```
#### Creating new element with `createElement`
```javascript
const li = document.createElement('li');
```
#### Remove child element with `removeChild`
```javascript
tasklist.removeChild(tasklist.firstChild);
```
we can also remove element with the use of only `remove()` method
```javascript
e.target.parentElement.parentElement.remove();
```
## March 26 2020 / DOM
---
### DOM project - Task manager (Completed)
#### `getItem()` returns value of the specified Storage Object item.
```javascript
tasks = JSON.parse(localStorage.getItem('tasks'));
```
#### Use of `JSON.parse()` to exchange data
JSON.parse() convert data to JS Object
```javascript
tasks = JSON.parse(localStorage.getItem('tasks'));
```

#### Use of `localStorage` to convert JS Object to String
Syntax: 
```javascript
myStorage = window.localStorage;

localStorage.setItem('tasks', JSON.stringify(tasks));
```
#### Use of `forEach` calls a function once for each element, for all `li` element with `collection-items` class it select in order
```javascript
document.querySelectorAll('.collection-items').forEach(function(task){
        const item = task.firstChild.textContent;
        if(item.toLowerCase().indexOf(text) != -1){
            task.style.display = 'block';
        }
        else{
            task.style.display = 'none';
        }
    });
```
#### Use `clear()` to remove all storage items
```javascript
function clearTaskFromLocalStorage(){
    localStorage.clear();
}
```
## March 27 2020 / DOM
---
### DOM project - Loan calculator
#### Use of `addEventListener` to attach event handler to element like `click` , `mouseover` , `mouseout` , `keyup` , `keydown` etc
```javascript
document.getElementById('submit').addEventListener('click', function(e){
    document.getElementById('results').style.display = 'none';

    e.preventDefault();
});
```
#### Use of `setTimeout` call function after specified time
```javascript
setTimeout(calculateResult, 2000);
```
#### Use fo `parseFloat` parse string and return float number
```javascript
const calculateInterest = parseFloat(interest.value) / 100 / 12;
```
#### Use of `math.POW()` takes value `a, b` and return `a `to the power `b`
```javascript
 const x = Math.pow(1 + calculateInterest, calculatePayment);
```
#### Use of `insertBefore` takes two element `a, b` and insert `a` element before `b`
```javascript
container.insertBefore(errorDiv, heading);
```
## March 28 2020 / Saturday
---
### Saturday
## March 29 2020 / OOP
---
### Creating object in JavaScript
#### Using object literal
```javascript
var person = {firstName:"Kishor", lastName:"Ghising"};
```
#### Using New keyword
```javascript
var person = new Object();
person.firstName = "Kishor";
person.lastName = "Ghising";
```
#### Using Constructor
```javascript
function Person(firstName, lastName) {
  this.firstName = firstName;
  this.lastName = lastName;
}
```
#### Use of `this` keyword and js method
`this` keyword refer to parent object

```javascript
var person = {
  firstName: "Kishor",
  lastName : "Ghising",
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};
```
#### Use of `class`
```javascript
class Name {
  constructor(name) {
    this.FullName = name;
  }
}
myname = new Name("Kishor Ghising");
```
## March 30 2020 / OOP booklist project(completed)
---
### Prototype in js
JavaScript objects inherit properties and methods from prototype
```javascript
// instantiate UI
    const ui = new UI();
// remove book from list
    ui.deleteBook(e.target)


// Remove list items
UI.prototype.deleteBook = function(target){
    if(target.className = 'delete'){
        target.parentElement.parentElement.remove();
    }
}
```
#### Use of `preventDefault()`
`preventDefault()` method cancels the event from default action
```javescript
  e.preventDefault();
```
#### Use java script ES6 Class to create Consturctor
```javascript
  class Book{
    constructor(title, author, isbn){
        this.title = title;
        this.author = author;
        this.isbn = isbn;
    }
  } 
```
## March 31 2020
---
### AsynchronousJS
#### `XMLHttpRequest()` used to request data from a web server.
```javascript
 const xhr = new XMLHttpRequest();
```
#### open() method opens a new browser window depending on your browser settings and the parameter values
Here `open()` is used to open txt and JSON file
```javascript
  xhr.open('GET', 'data.txt', true);
  xhr.open('GET', 'employee.json', true);
```
#### `responseText` returns the text received from a server following a request being `send()`
```javascript
  xhr.onload = function(){
      if(this.status == 200){
          document.getElementById('data').innerHTML = `
              <h1>${this.responseText}<h1/>
          `;
      }
    }
    xhr.send(); 
```
#### AJAX server response
| property      | Description           |
| :------------- |:-------------| 
|   readyState     | Holds the status of the XMLHttpRequest.
||0: request not initialized 
||1: server connection established
||2: request received
||3: processing request
||4: request finished and response is ready | 
| status      | 200: "OK"
||403: "Forbidden"
||404: "Page not found" |

#### Checking server response<br/>
-parsing one JSON object
```javascript
  if(this.status == 200){
      const employee = JSON.parse(this.response);
      const output = `
          <ul>
              <li>ID: ${employee.id}</li>
              <li>Name: ${employee.name}</li>
              <li>Company: ${employee.company}</li>
          </ul>
      `;
      document.getElementById('employee').innerHTML = output;
  }
```
-parsing one JSON object using `forEach`
```javascript
  if(this.status == 200){
    const employees = JSON.parse(this.response);
    let output = '';
    employees.forEach(function(employee){
        output += `
        <ul>
            <li>ID: ${employee.id}</li>
            <li>Name: ${employee.name}</li>
            <li>Company: ${employee.company}</li>
        </ul>
    `;
    });
    document.getElementById('employees').innerHTML = output;
}
```
## March 1 2020
---
