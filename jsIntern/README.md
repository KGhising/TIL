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