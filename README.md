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
```html
<div id="app"></div>
```

CSS
```css
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
```js
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
```js
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
```js
function myFunc(){
    ...
}
```

```js
const myFunc = () => {
    ...
}
```

No more issues with the **this** keyword!

```js
const printMyName = name => {
    console.log(name)
}

printMyName('Max');

const multiply = number => number * 2;

console.log(multiply(2));
```

### Exports and Imports (Modules)

person.js
```js
const person = {
    name: 'Max' 
}

export default person
```

utility.js
```js
export const clean = () => {...}
export const baseData = 10;
```

app.js
```js
import person from './person.js'
import prs from './person.js'

import {baseData} from './utility.js'
import {clean} from './utility.js'
```

- default export - You choose the name
- named export - Name is defined by export

### Understanding Classes

**Classes**
```js
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
```js
const person = new Person()
person.printMyName();
```

Inheritance
```js
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
```js
constructor() {
    this.myProperty = 'value'
}
```

ES7
```js
myProperty = 'value'
```

ES6
```js
myMethod() {...}
```

ES7
```js
myMethod = () => {...}
```

Choose Babel from the JavaScript Menu

```js
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

```js
const newArray = [...oldArray, 1, 2]
const newObject = {...oldObject, newProp:5}
```


- Rest - Used to merge a list of function arguments into an array

```js
function sortArgs(...args) {
    return args.sort()
}
```

http://jsbin.com/?html,output

```js
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
```js
[a, b] = ['Hello', 'Max']
console.log(a) //Hello
console.log(b) //Max
```

- Object Destructuring
```js
{name} = {name:'Max', age:28}
console.log(name) //Max
console.log(age) //undefined
```

http://jsbin.com/?html,output

```js
const numbers = [1, 2, 3];
[num1, ,num3] = numbers;
console.log(num1, num3)
```

### Reference and Primitive Types Refresher

http://jsbin.com/?html,output

```js
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

```js
const numbers = [1, 2, 3];

const doubleNumArray = numbers.map(() => {
    return num * 2;
});

console.log(numbers);
console.log((doubleNumArray));
```

### Summary

In this module, I provided a brief introduction into some core next-gen JavaScript features, of course focusing on the ones you'll see the most in this course. Here's a quick summary!

**let & const**
Read more about `let` : https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let

Read more about `const` : https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const

`let`  and `const`  basically replace `var` . You use `let`  instead of `var`  and `const`  instead of `var`  if you plan on never re-assigning this "variable" (effectively turning it into a constant therefore).

**ES6 Arrow Functions**
Read more: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions

Arrow functions are a different way of creating functions in JavaScript. Besides a shorter syntax, they offer advantages when it comes to keeping the scope of the `this` keyword (see here https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions#No_binding_of_this).

Arrow function syntax may look strange but it's actually simple.
```js
function callMe(name) { 
    console.log(name);
}
```
which you could also write as:
```js
const callMe = function(name) { 
    console.log(name);
}
```
becomes: 
```js
const callMe = (name) => { 
    console.log(name);
}
```
**Important:**

When having **no arguments**, you have to use empty parentheses in the function declaration:
```js
const callMe = () => { 
    console.log('Max!');
}
```
When having **exactly one argument**, you may omit the parentheses:
```js
const callMe = name => { 
    console.log(name);
}
```
When **just returning a value**, you can use the following shortcut:
```js
const returnMe = name => name
```
That's equal to:
```js
const returnMe = name => { 
    return name;
}
```
**Exports & Imports**
In React projects (and actually in all modern JavaScript projects), you split your code across multiple JavaScript files - so-called modules. You do this, to keep each file/ module focused and manageable.

To still access functionality in another file, you need `export`  (to make it available) and `import`  (to get access) statements.

You got two different types of exports: **default** (unnamed) and **named** exports:

**default** => `export default ...;`

**named** => `export const someData = ...;`

You can import **default exports** like this:

`import someNameOfYourChoice from './path/to/file.js';`

Surprisingly, `someNameOfYourChoice`  is totally up to you.

**Named exports** have to be imported by their name:

`import { someData } from './path/to/file.js';`

A file can only contain one default and an unlimited amount of named exports. You can also mix the one default with any amount of named exports in one and the same file.

When importing **named exports**, you can also import all named exports at once with the following syntax:

`import * as upToYou from './path/to/file.js';`

`upToYou`  is - well - up to you and simply bundles all exported variables/functions in one JavaScript object. For example, if you `export const someData = ...`  (`/path/to/file.js` ) you can access it on `upToYou`  like this: `upToYou.someData` .

**Classes**
Classes are a feature which basically replace constructor functions and prototypes. You can define blueprints for JavaScript objects with them. 

Like this:
```js
class Person {
    constructor () {
        this.name = 'Max';
    }
}
 
const person = new Person();
console.log(person.name); // prints 'Max'
```
In the above example, not only the class but also a property of that class (=> `name` ) is defined. The syntax you see there, is the "old" syntax for defining properties. In modern JavaScript projects (as the one used in this course), you can use the following, more convenient way of defining class properties:
```js
class Person {
    name = 'Max';
}
 
const person = new Person();
console.log(person.name); // prints 'Max'
```
You can also define methods. Either like this:
```js
class Person {
    name = 'Max';
    printMyName () {
        console.log(this.name); // this is required to refer to the class!
    }
}
 
const person = new Person();
person.printMyName();
```
Or like this:
```js
class Person {
    name = 'Max';
    printMyName = () => {
        console.log(this.name);
    }
}
 
const person = new Person();
person.printMyName();
```
The second approach has the same advantage as all arrow functions have: The `this`  keyword doesn't change its reference.

You can also use **inheritance** when using classes:
```js
class Human {
    species = 'human';
}
 
class Person extends Human {
    name = 'Max';
    printMyName = () => {
        console.log(this.name);
    }
}

const person = new Person();
person.printMyName();
console.log(person.species); // prints 'human'
```
**Spread & Rest Operator**
The spread and rest operators actually use the same syntax: `...` 

Yes, that is the operator - just three dots. It's usage determines whether you're using it as the spread or rest operator.

**Using the Spread Operator:**

The spread operator allows you to pull elements out of an array (=> split the array into a list of its elements) or pull the properties out of an object. Here are two examples:
```js
const oldArray = [1, 2, 3];
const newArray = [...oldArray, 4, 5]; // This now is [1, 2, 3, 4, 5];
```
Here's the spread operator used on an object:
```js
const oldObject = {
    name: 'Max'
};
const newObject = {
    ...oldObject,
    age: 28
};
```
`newObject`  would then be
```js
{
    name: 'Max',
    age: 28
}
```
The spread operator is extremely useful for cloning arrays and objects. Since both are reference types (and not primitives), copying them safely (i.e. preventing future mutation of the copied original) can be tricky. With the spread operator you have an easy way of creating a (shallow!) clone of the object or array. 

**Destructuring**
Destructuring allows you to easily access the values of arrays or objects and assign them to variables.

Here's an example for an array:
```js
const array = [1, 2, 3];
const [a, b] = array;
console.log(a); // prints 1
console.log(b); // prints 2
console.log(array); // prints [1, 2, 3]
```
And here for an object:
```js
const myObj = {
    name: 'Max',
    age: 28
}
const {name} = myObj;
console.log(name); // prints 'Max'
console.log(age); // prints undefined
console.log(myObj); // prints {name: 'Max', age: 28}
```
Destructuring is very useful when working with function arguments. Consider this example:
```js
const printName = (personObj) => {
    console.log(personObj.name);
}
printName({name: 'Max', age: 28}); // prints 'Max'
```
Here, we only want to print the name in the function but we pass a complete person object to the function. Of course this is no issue but it forces us to call personObj.name inside of our function. We can condense this code with destructuring:
```js
const printName = ({name}) => {
    console.log(name);
}
printName({name: 'Max', age: 28}); // prints 'Max')
```
We get the same result as above but we save some code. By destructuring, we simply pull out the name  property and store it in a variable/ argument named name  which we then can use in the function body.

### JS Array Functions

Not really next-gen JavaScript, but also important: JavaScript array functions like `map()` , `filter()` , `reduce()`  etc.

You'll see me use them quite a bit since a lot of React concepts rely on working with arrays (in immutable ways).

The following page gives a good overview over the various methods you can use on the array prototype - feel free to click through them and refresh your knowledge as required: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array

Particularly important in this course are:

- `map()`  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
- `find()`  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find
- `findIndex()`  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex
- `filter()`  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
- `reduce()`  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=b
- `concat()`  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/concat?v=b
- `slice()`  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice
- `splice()`  => https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice

## Understanding the Base Features & Syntax

### The Build Workflow

**WHY?**
- Recomendded for SPAs and MPAs
- **Optimize** Code
- Use **Next-Gen** JavaScript Features (ES6 vs ES5)
- Be **More Productive**

**HOW?**
- Use **Dependency Management** Tool - **npm** or **yarn**
- Use **Bundler** - Recommended: **Webpack**
- Use **Compiler** (Next-Gen JavaScript) - **Babel** + Presets
- Use a **Development Server**

### Using Create React App

Install NodeJS
https://nodejs.org/en/

https://github.com/facebook/create-react-app

```
npx create-react-app react-complete-guide --scripts-version 1.1.5
cd react-complete-guide
npm start
```
