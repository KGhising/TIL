# TIL for java script intern
***
## March 23 2020
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