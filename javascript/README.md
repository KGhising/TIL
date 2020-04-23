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
## April 1 2020
---
### Custom HTTP library
#### Get post from library using `get`
```javascript
  const http = new HTTP;

    // GET post
    http.get('https://jsonplaceholder.typicode.com/posts', function(err, posts){
        if(err){
            console.log(err);
        }    
        else{
            console.log(posts);
        }
    });
```
#### Create post on library using `post`
```javascript
  // Create data
  const data = {
      title: 'Custom post',
      body: 'Custom body'
  };

  //create POST
  http.post('https://jsonplaceholder.typicode.com/posts', data, function(err, posts){
      if(err){
          console.log(err);
      }    
      else{
          console.log(posts);
      }
  });
```
#### Update post on library using `put`
```javascript
  // Update Post
  http.put('https://jsonplaceholder.typicode.com/posts/1', data, function(err, posts){
      if(err){
          console.log(err);
      }    
      else{
          console.log(posts);
      }
  });
```
#### Delete post on library using `delete`
```javascript
  // delete data
  http.delete('https://jsonplaceholder.typicode.com/posts/1', function(err, response){
      if(err){
          console.log(err);
      }    
      else{
          console.log(response);
      }
});
```
#### Asynchronous `callbacks` function
Asynchronous callbacks are functions specified as arguments when calling a function which will start executing code in the background
```javascript
// callback function
  function createPost(post, callback){
    setTimeout(function(){
        posts.push(post);
        callback();
    }, 2000);
}
```
#### Use of `promise`
A promise is an object that may produce a single value some time in the future: either a resolved value, or a reason that it’s not resolved (reject)
Promise has four states
* fulfilled
* rejected
* pending
* settled
```javascript
  // creating post/ promise
  function createPost(post, ){
    return new Promise(function(resolve, reject){
        setTimeout(function(){
            posts.push(post);

            const err = true;
            if(!err){
                resolve();
            }else{
                reject('Error: something wrong');
            }
        }, 2000);
    });
  }
```
## April 2 2020 / Github finder
---
### Github API project - Github finder
#### Fetching profile and repo from Github API
```javascript
  class Github{
    constructor(){
        this.client_id = '723a22a7550702eab411' ;
        this.client_secret = 'f1f04d945fb20c7f91694aa3666bfc1fac2937f9';
        this.repos_count = 5;
        this.repos_sort = 'created: asc';
    }
    async getUser(user){
        // fetch profile
        const profileResopnse = await fetch(`https://api.github.com/users/${user}?client_id=${this.client_id}&client_secret=${this.client_secret}`);

        // fetch repo
        const repoResopnse = await fetch(`https://api.github.com/users/${user}/repos?per_page=${this.repos_count}&sort=${this.repos_sort}&client_id=${this.client_id}&client_secret=${this.client_secret}`);
        
        const profile = await profileResopnse.json();
        const repos = await repoResopnse.json();
        return{
            profile,
            repos
        }
    }
}
```
### April 3, 5 2020 / Weather Project
---
#### Loading DOM
```javascript
    // get weather on DOM load
    document.addEventListener('DOMContentLoaded', getWeather);
```
#### Fetcching Weather from openWeather API
```javascript
    
class Weather {
    constructor(){
        this.apiKey = '82005d27a116c2880c8f0fcb866998a0';
        this.city = 'Kathmandu';
    }

    // fetch weather from API
    async getWeather(){
        const response = await fetch(`https://api.openweathermap.org/data/2.5/weather?q=${this.city}&appid=${this.apiKey}`);

        const responseData = await response.json();
        return responseData;   
    }
    // change weather Location
    changeLocation(city){
        this.city = city;
    }
} 
```
### April 6 2020 / Error handliing
---
#### types of error
* reference error
* type error
* syntax error  
* URI error

```javascript
    // reference error
    myFunction();

    // type error
    null.myFunction();

    // syntax error
    eval('Hello World');

    // URI error
    decodeURIComponent('%');
```

#### Error handling with try and catch
```javascript
    try{
        if(!user.name){
            // throw 'User has no name';
            throw new SyntaxError('User has no name');
        }

    }
    catch(e){
        // console error
        console.log(e);

        // console error name
        console.log(e.name);

        // console error messsage
        console.log(e.message);

        // console to check if its this error
        console.log(e instanceof ReferenceError);
    }

```
### Regular expression
#### evaluation function
```javascript
    // Regular expression write inside /...../ 
    let re;
    re = /hello/;
    re = /hello/i; // `i` makes case insensitive
```
#### Use of `exec()`
```javascript
    // exec() function will return result in array if there is matchor null
    const result = re.exec('Wow, hello world');
    console.log(result);
    console.log(result[0]);
    console.log(result.index);
    console.log(result.input);
```
#### Use of `test()`
```javascript
    // test() function return true or false
    const result = re.test('Hello');
    console.log(result);
```
#### Use of `match()`
```javascript
    // match() function will return result array or null
    const str = 'hello world';
    const result = str.match(re);
    console.log(result);
```
#### Use of `search()`
```javascript
    // search() function return index of first match if not found return -1
    const str = 'hello worlds';
    const result = str.search(re);
    console.log(result);
```
#### Use of `replace()`
```javascript
    // replace() will return new string with some or all matches of a pattern
    const str = 'hello worlds';
    const newStr = str.replace(re, 'hi');
    console.log(newStr)
```
#### Use of metaCharacter symbol
```javascript
    // meta character symbol
    re = /^h/i; // ^ must start with
    re = /d$/i; // $ must ends with
    re = /^hello$/i; // must start and end with hello
    re = /h.llo/i; // . match any one character
    re = /h*llo/i; // * match any character 0 or more times
    re = /gre?a?y/i; // ? optionalcharacter a and e
    re = /gre?a?y\?/i; // \ escape character character

    // Brackets [] character sets
    re = /gr[ae]y/i; // must be a or e
    re = /[GF]ray/; // must be G or F
    re = /[^GF]ray/; // Match except G or F
    re = /[A-Z]ray/; // Match any uppercase character between A-Z  
    re = /[a-zA-Z]ray/; // Match any character between a-z or A-Z
    re = /[0-9]ray/; // Match any digit between

    // Braces {} -Quantifier
    re = /hel{2}o/i; // must occur exactly {m} times
    re = /hel{2,4}o/i; // must occur exactly between {n,m} times
    re = /hel{2,}o/i; // must occur atleast between {m,} times

    // parethesis () -grouping
    re = /([0-9]x){3}/; // Grouping [0-9]x 

    // shorthand character classes
    re = /\w/; // Word character - alphanumeric
    re = /\w+/; // + 1 or more character
    re = /\W/; // non-word character
    re = /\d/; // match any digit 
    re = /\d+/; // match any digit 0 or more times
    re = /\D/; // match any non-digit
    re = /\s/; // match white space character
    re = /\S/; // match white non-space character
    re = /hell\b/i; // world boundary

    // assertion
    re = /x(?=y)/; // match x only if its followed by y
    re = /x(?!y)/; // match x only if its not-followed by y
```
#### Form validation
* Name: /^[a-zA-Z]{2,10}$/
* Zipcode: /^[0-9]{5}(-[0-9]{4})?$/
* Email: /^([a-zA-Z0-9_\-\.]+)@([a-zA-Z0-9_\-\.]+)\.([a-zA-Z]{2,5})$/
* Number: ^\(?\d{3}\)?[- ]?\d{3}[- ]\d{4}$/

### April 7 2020 / ES6 features
---
#### Iterators are an implementation of Iterable objects such as maps, arrays and strings which enables us to iterate over them using `next()`
```javascript
    function nameIterator(names) {
      let nextIndex = 0;

      return {
        next: function() {
          return nextIndex < names.length ?
          { value: names[nextIndex++], done: false } :
          { done: true }
        }
      }
    // Create an array of names
    const namesArr = ['Jack', 'Jill', 'John'];
    // Init iterator and pass in the names array
    const names = nameIterator(namesArr);
    console.log(names.next().value);
```
#### Generator Functions on the other hand, “run until yield/return/end”
```javascript
    // ID Creator
    function* createIds() {
    let index = 1;

    while(true) {
        yield index++;
    }
    }

    const gen = createIds();

    console.log(gen.next().value);
```
#### Destructuring is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.
```javascript
    // Object Destructuring
    const person = {
    name: 'kishor',
    age: 21,
    city: 'bhaktapur',
    gender: 'Male',
    sayHello: function(){
        console.log('Hello');
    }
    }
    // Old ES5
    // const name = person.name,
    //       age = person.age,
    //       city = person.city;

    // New ES6 Destructuring
    const { name, age, city, sayHello } = person;
    console.log(name, age, city);
    sayHello();
``` 
#### `Map()` Map is a collection of elements where each element is stored as a Key, value pair.
```javascript
    const map1 = new Map();
    // Set Keys
    const key1 = 'some string',
        key2 = {},
        key3 = function() {};
    // Set map values by key
    map1.set(key1, 'Value of key1');
    map1.set(key2, 'Value of key2');
    map1.set(key3, 'Value of key3');

    console.log(map1.get(key1), map1.get(key2), map1.get(key3));
```
#### `Set()` Sets are a new object type included in ES6 that allow the creation of collections of unique values
```javascript
    const set1 = new Set();

    // Add values to set
    set1.add(100);
    set1.add('A string');
    set1.add({name: 'John'});
    set1.add(true);
    set1.add(100);

    const set2 = new Set([1, true, 'string']);
    console.log(set2);
    console.log(set1);
```

#### `Symbols()` Once you create a symbol, its value is kept private and for internal use but can access through method in `return`
```javascript
    // unique object key
    const KEY1 = Symbol();
    const KEY2 = Symbol('sym2');

    const obj = {};

    obj[KEY1] = 'prop1';
    obj[KEY2] = 'prop2';
    obj.key3 = 'prop3';
    obj.key4 = 'prop4';

    // console.log(obj[KEY1]);
    // symbols are not counted in for....in
    for(let i in obj){
        console.log(`${i}: ${obj[i]}`);
    }

    // Symbol are ignored by JSON.stringify()
    console.log(JSON.stringify({key: 'prop'}));
    console.log(JSON.stringify({[Symbol('sym')]: 'prop'}));
```
### April 8 2020 / Trace Calories project
---
#### Project Overview
This application track your Calorie consumtion and store data in local storage
#### Features
* Add food items and calories
* Can edit your data
* Delete data from local storage
*  You ca clear all data
*  Calculate your calories

#### Project Implementation
It has four Controller
* Storage 
* Items
* UI
* App Controller