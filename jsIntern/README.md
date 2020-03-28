# TIL for java script intern
***
## March 23  2020 / Fundamentals
---
### Using console `console`

```
console.log('Hello'); 
```
### Single selector `getElementByID` , `querySelector`

```
document.getElementById('idSelector');
document.querySelector('li').style.color = 'yellow';
document.querySelector('.select').style.color = "red";
document.querySelector('#select').style.color = "green"

```
### Multiple selector `getElementByClassName` , `querySelectorAll` , `getElementByName` , `getElementByTagName`

### Type conversion

| Method        | Desxcription           |
| :------------- |:-------------| 
|   toString()     | Convert to string | 
| String(x)      | Convert number into String      |
| toFixed() | Fixed number rounded with given specific number |
| Number('text') | Convert text into number |
| Number(false/true) | Convert booleans to number 0/1 |

### String Concatination `concat()`
```
var str1 = "Hello ";
var str2 = "world!";
var res = str1.concat(str2);

string.concat(Hello, world!);
```
## March 24 2020 / DOM
---
### Using `innerHTML` to add `text` in selector `id` and `style`
```
const selector = document.getElementById('idSelector');
selector.innerHTML = 'Things i did today!';
selector.style.color = "skyblue";
```
### Styling `li` items using `tag` , `class` , `id` selector
```
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

## Appending child in parent tag with `appendChild`
```
li.appendChild(document.createTextNode(taskInput.value));
```
## Creating new element with `createElement`
```
const li = document.createElement('li');
```
## Remove child element with `removeChild`
```
tasklist.removeChild(tasklist.firstChild);
```
we also can remove element with the use of only `remove()` method
```
e.target.parentElement.parentElement.remove();
```
## March 26 2020 / DOM
---
DOM project - Task manager (Completed)
## `getItem()` returns value of the specified Storage Object item.
```
tasks = JSON.parse(localStorage.getItem('tasks'));
```
## Use of `JSON.parse()` to exchange data
JSON.parse() convert data to JS Object
```
tasks = JSON.parse(localStorage.getItem('tasks'));
```
## Use of `JSON.parse()` to exchange data

## Use of `localStorage` to convert JS Object to String
Syntax: 
```
myStorage = window.localStorage;

localStorage.setItem('tasks', JSON.stringify(tasks));
```
## Use of `forEach` , calls a function once for each element, for all `li` element with `collection-items` class it select in order
```
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
## Use `clear()` to remove all storage items
```
function clearTaskFromLocalStorage(){
    localStorage.clear();
}
```