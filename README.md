# react-complete-guide

## Getting Started

### What is React?

"A JavaScript Library for building User Interfaces"

**Components?**

- Header Component
- Sidebar Component
- Headline Component
- Article Content Component

### Real-World SPAs & React Web Apps

https://reactjs.org/

### Writing our First React Code

https://codepen.io/

Settings => JavaScript
JavaScript Preprocessor: Babel
Add: react, react-dom

HTML
```
<div id="app"></div>
```

CSS
```
.person {
  display: inline-block;
  margin: 10px;
  border: 1px solid #eee;
  box-shadow: 0 2px 2px #ccc;
  width: 200px;
  padding: 20px;
}
```

JS
```
function Person(props) {
  return(
    <div className="person">
      <h1>{props.name}</h1>
      <p>Your Age: {props.age}</p>
    </div>
  );
}

var app = (
  <div>
    <Person name="Max" age="28" />
    <Person name="Manu" age="29" />
  </div>
);

ReactDOM.render(app,
document.querySelector('#app'));
```

### Why Should we Choose React?

- UI State becomes dificult to handle with Vanilla JavaScript
- Focus on Business Logic, not on preventing your App from exploding (Plus: Framework Creators probably write better Code)
- Huge Ecosystem, Active Community, High Performance

### React Alternatives

- React
- Angular
- Vue

### Understanding Single Page Application and Multi Page Applications

Single Page Applications:
- Only ONE HTML Page, Content is (re)rendered on Client
- Typically only ONE ReactDOM.render() call


Multi Page Applications
- Multiple HTML Pages, Content is rendered on Server
- One ReactDOM.render() call per "widget"

### Course Outline 
- Getting Started
- The Basics
- Debugging
- Styling Components
- Components Deep Dive
- HTTP Requests
- Routing
- Forms & Validation
- Redux
- Authentication
- Testing Introduction
- Deployment
- Bonus (Animations, Next Steps, Webpack)

### How to get the Most out of this Course
- Code along!
- Check the Source Code
- Ask & Answeer in Q&A
- Practice, Practice, Practice

## Refreshing Next Generation JavaScript (Optional)

### Understanding "let" and "const"
- var
- let - variable values
- const - constant values

http://jsbin.com/?html,output

JavaScript
```
const myName = 'Max'
console.log(myName)

myName = 'Manu'
console.log(myName)

let yourName = 'Max'
console.log(yourName)

myName = 'Manu'
console.log(yourName)
```

### Arrow Functions
```
function myFunc(){
    ...
}
```

```
const myFunc = () => {
    ...
}
```

No more issues with the **this** keyword!

```
const printMyName = name => {
    console.log(name)
}

printMyName('Max');

const multiply = number => number * 2;

console.log(multiply(2));
```

### Exports and Imports (Modules)

person.js
```
const person = {
    name: 'Max' 
}

export default person
```

utility.js
```
export const clean = () => {...}
export const baseData = 10;
```

app.js
```
import person from './person.js'
import prs from './person.js'

import {baseData} from './utility.js'
import {clean} from './utility.js'
```

- default export - You choose the name
- named export - Name is defined by export

### Understanding Classes

**Classes**
```
class Person {
    constructor() {
        this.name = 'Max';
    }

    printMyName() {
        console.log(this.name);
    }
}
```

Usage (constructor functions anyone?)
```
const person = new Person()
person.printMyName();
```

Inheritance
```
class Human {
    constructor() {
        this.gender = 'male';
    }

    printGender () {
        console.log(this.gender);
    }
}

class Person extends Human {
    constructor() {
        super();
        this.name = 'Max';
    }

    printMyName () {
        console.log(this.name);
    }
}

const person = new Person()
person.printMyName();
person.printGender();
```

### Classes, Properties and Methods
- Properties are like "variables attached to classes/objects"
- Methods are like "functions attached to classes/object"

ES6
```
constructor() {
    this.myProperty = 'value'
}
```

ES7
```
myProperty = 'value'
```

ES6
```
myMethod() {...}
```

ES7
```
myMethod = () => {...}
```

Choose Babel from the JavaScript Menu

```
class Human {
    gender = 'male';

    printGender = () => {
        console.log(this.gender);
    }
}

class Person extends Human {
    name = 'Max';

    printMyName = () =>{
        console.log(this.name);
    }
}

const person = new Person()
person.printMyName();
person.printGender();
```

### The Spread & Rest Operator
`...`

- Spread - Used to split up array elements OR object properties

```
const newArray = [...oldArray, 1, 2]
const newObject = {...oldObject, newProp:5}
```


- Rest - Used to merge a list of function arguments into an array

```
function sortArgs(...args) {
    return args.sort()
}
```

http://jsbin.com/?html,output

```
const numbers = [1, 2, 3];
const newNumbers = [...numbers, 4];

console.log(newNumbers);

const person = {
    name: 'Max'
}

const newPerson = {
    ...person,
    age: 28
}

console.log(newPerson);

const filter = (...args) => {
    return args.filter(el => el === 1);
}

console.log(filter(1, 2, 3));
```

### Destructuring
Easily extract elements or object properties and store them in variables

- Array Destructuring
```
[a, b] = ['Hello', 'Max']
console.log(a) //Hello
console.log(b) //Max
```

- Object Destructuring
```
{name} = {name:'Max', age:28}
console.log(name) //Max
console.log(age) //undefined
```

http://jsbin.com/?html,output

```
const numbers = [1, 2, 3];
[num1, ,num3] = numbers;
console.log(num1, num3)
```

### Reference and Primitive Types Refresher

http://jsbin.com/?html,output

```
const number = 1;
const num2 = number;

console.log(num2);

const person = {
    name: 'Max' 
};

const secondPerson = person;

person.name = 'Manu';

console.log(secondPerson)

const secondPerson = {
    ...person
};

person.name = 'Manu';

console.log(secondPerson)
```

### Refreshing Array Functions

