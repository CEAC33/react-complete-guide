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

### Components & JSX Cheat Sheet

Components are the **core building block of React apps**. Actually, React really is just a library for creating components in its core.

A typical React app therefore could be depicted as a **component tree** - having one root component ("App") and then an potentially infinite amount of nested child components.

Each component needs to return/ render some **JSX** code - it defines which HTML code React should render to the real DOM in the end.

**JSX is NOT HTML** but it looks a lot like it. Differences can be seen when looking closely though (for example className in JSX vs class in "normal HTML"). JSX is just syntactic sugar for JavaScript, allowing you to write HTMLish code instead of nested React.createElement(...) calls.

When creating components, you have the choice between **two different ways:**

1.- **Functional components** (also referred to as "presentational", "dumb" or "stateless" components - more about this later in the course) => `const cmp = () => { return <div>some JSX</div> }` (using ES6 arrow functions as shown here is recommended but optional)

2.- **class-based components** (also referred to as "containers", "smart" or "stateful" components) => `class Cmp extends Component { render () { return <div>some JSX</div> } }` 
We'll of course dive into the difference throughout this course, you can already note that you should use 1) as often as possible though. It's the best-practice.

### Props & State
`props`  and `state`  are **CORE concepts** of React. Actually, only changes in `props`  and/ or `state`  trigger React to re-render your components and potentially update the DOM in the browser (a detailed look at how React checks whether to really touch the real DOM is provided in section 6).

**Props**

`props`  allow you to pass data from a parent (wrapping) component to a child (embedded) component.

**Example:**

**AllPosts Component:**

```js
const posts = () => {
    return (
        <div>
            <Post title="My first Post" />
        </div>
    );
}
```

Here, `title`  is the custom property ( `prop` ) set up on the custom `Post` component. We basically replicate the default HTML attribute behavior we already know (e.g. `<input type="text">` informs the browser about how to handle that input).

**Post Component:**

```js
const post = (props) => {
    return (
        <div>
            <h1>{props.title}</h1>
        </div>
    );
}
```

The `Post` component receives the `props` argument. You can of course name this argument whatever you want - it's your function definition, React doesn't care! But React will pass one argument to your component function => An object, which contains all properties you set up on `<Post ... />` .

`{props.title}` then dynamically outputs the `title` property of the `props`  object - which is available since we set the `title` property inside `AllPosts` component (see above).



**State**

Whilst props allow you to pass data down the component tree (and hence trigger an UI update), state is used to change the component, well, state from within. Changes to state also trigger an UI update.

**Example:**

**NewPost Component:**

```js
class NewPost extends Component { // state can only be accessed in class-based components!
    state = {
        counter: 1
    };  
 
    render () { // Needs to be implemented in class-based components! Needs to return some JSX!
        return (
            <div>{this.state.counter}</div>
        );
    }
}
```

Here, the `NewPost` component contains `state`. Only class-based components can define and use `state`. You can of course pass the `state` down to functional components, but these then can't directly edit it.

`state` simply is a property of the component class, you have to call it `state` though - the name is not optional. You can then access it via `this.state` in your class JSX code (which you return in the required `render()` method).

Whenever `state` changes (taught over the next lectures), the component will re-render and reflect the new state. The difference to `props` is, that this happens within one and the same component - you don't receive new data ( `props` ) from outside!

### To Which Events Can You Listen?

In the last lecture, we saw that you can react to the onClick event - but to which other events can you listen? You can find a list of supported events here: https://reactjs.org/docs/events.html#supported-events

**Clipboard Events**

Event names:
```
onCopy onCut onPaste
```

Properties:
```
DOMDataTransfer clipboardData
```

**Composition Events**

Event names:
```
onCompositionEnd onCompositionStart onCompositionUpdate
```

Properties:
```
string data
```

**Keyboard Events**

Event names:
```
onKeyDown onKeyPress onKeyUp
```

Properties:
```
boolean altKey
number charCode
boolean ctrlKey
boolean getModifierState(key)
string key
number keyCode
string locale
number location
boolean metaKey
boolean repeat
boolean shiftKey
number which
```

**Focus Events**

Event names:
```
onFocus onBlur
```

These focus events work on all elements in the React DOM, not just form elements.

Properties:
```
DOMEventTarget relatedTarget
```

**Form Events**

Event names:
```
onChange onInput onInvalid onSubmit
```

For more information about the onChange event, see Forms.

**Mouse Events**

Event names:
```
onClick onContextMenu onDoubleClick onDrag onDragEnd onDragEnter onDragExit
onDragLeave onDragOver onDragStart onDrop onMouseDown onMouseEnter onMouseLeave
onMouseMove onMouseOut onMouseOver onMouseUp
```

The `onMouseEnter` and `onMouseLeave` events propagate from the element being left to the one being entered instead of ordinary bubbling and do not have a capture phase.

Properties:
```
boolean altKey
number button
number buttons
number clientX
number clientY
boolean ctrlKey
boolean getModifierState(key)
boolean metaKey
number pageX
number pageY
DOMEventTarget relatedTarget
number screenX
number screenY
boolean shiftKey
```

**Selection Events**

Event names:
```
onSelect
```

**Touch Events**

Event names:
```
onTouchCancel onTouchEnd onTouchMove onTouchStart
```

Properties:
```
boolean altKey
DOMTouchList changedTouches
boolean ctrlKey
boolean getModifierState(key)
boolean metaKey
boolean shiftKey
DOMTouchList targetTouches
DOMTouchList touches
```

**UI Events**


Event names:
```
onScroll
```

Properties:
```
number detail
DOMAbstractView view
```

**Wheel Events**

Event names:
```
onWheel
```

Properties:
```
number deltaMode
number deltaX
number deltaY
number deltaZ
```

**Media Events**

Event names:
```
onAbort onCanPlay onCanPlayThrough onDurationChange onEmptied onEncrypted
onEnded onError onLoadedData onLoadedMetadata onLoadStart onPause onPlay
onPlaying onProgress onRateChange onSeeked onSeeking onStalled onSuspend
onTimeUpdate onVolumeChange onWaiting
```

**Image Events**

Event names:
```
onLoad onError
```

**Animation Events**

Event names:
```
onAnimationStart onAnimationEnd onAnimationIteration
```

Properties:
```
string animationName
string pseudoElement
float elapsedTime
```

**Transition Events**

Event names:
```
onTransitionEnd
```

Properties:
```
string propertyName
string pseudoElement
float elapsedTime
```

**Other Events**

Event names:
```
onToggle
```

### Function Components Naming

In the **next lecture**, we'll learn how to manage state in functional components (instead of class-based components).

In case you're getting an error with the code shown in the next lecture, simply assign a capitalized variable name to the variable that holds your functional component.

**Example:**

Use
```js
const App = () => { ... }
```
instead of
```js
const app = () => { ... }
```
Technically, that's not required but depending on your project setup, the built-in linter (a code quality checking tool) that comes with create-react-app might not like the lowercase variable name.

You can also avoid this by creating projects with the **right react-scripts version**, which I would **recommend for this course** anyways
```
create-react-app my-app --scripts-version 1.1.5
```

### Using the useState() Hook for State Manipulation

App.js
```js
import React, { useState } from 'react';
import './App.css';
import Person from './Person/Person.js';

const app = props => {
  const [ personsState, setPersonsState] = useState({
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ]
  });

  const [otherState, setOtherState] = useState('some other value');

  console.log(personsState, otherState);

  const switchNameHandler = () => {
    // console.log('Was clicked!');
    // DON'T DO THIS this.state.persons[0].name = 'Maximilian';
    setPersonsState({
      persons: [
        { name: 'Maximilian', age: 28 },
        { name: 'Manu', age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }  

  return (
    <div className="App">

      <h1>Hi I'm a React App</h1>
      <p>This is really working</p>
      <button onClick={switchNameHandler}>Switch Name</button>
      <Person 
        name={personsState.persons[0].name} 
        age={personsState.persons[0].age}
      />
      <Person 
        name={personsState.persons[1].name} 
        age={personsState.persons[1].age}
        >
        My Hobbies: Racing
      </Person>
      <Person 
        name={personsState.persons[2].name} 
        age={personsState.persons[2].age}
      />
    </div>
  );
  // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hi, I\'m a React App!!!'));
}

export default app;
```

Person.js
```js
import React from 'react';

const person = ( props ) => {
    return (
        <div>
            <p>I'm {props.name} and I am {props.age} years old!</p>
            <p>{props.children}</p>
        </div>
    )
}

export default person;
```

### Stateless vs Stateful Components

Have as many pure functional presentational components as possible and only use state no matter how in a few selected components 

Container Component = Stateful Component = Smart Component
Presentational Component = Stateless Component = Dumb Component

### Passing Method References Between Components

App.js
```js
import React, { useState } from 'react';
import './App.css';
import Person from './Person/Person.js';

const app = props => {
  const [ personsState, setPersonsState] = useState({
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ]
  });

  const [otherState, setOtherState] = useState('some other value');

  console.log(personsState, otherState);

  const switchNameHandler = (newName) => {
    // console.log('Was clicked!');
    // DON'T DO THIS this.state.persons[0].name = 'Maximilian';
    setPersonsState({
      persons: [
        { name: newName, age: 28 },
        { name: 'Manu', age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }  

  return (
    <div className="App">

      <h1>Hi I'm a React App</h1>
      <p>This is really working</p>
      <button onClick={() => switchNameHandler('Maximilian!!!')}>Switch Name</button>
      <Person 
        name={personsState.persons[0].name} 
        age={personsState.persons[0].age}
      />
      <Person 
        name={personsState.persons[1].name} 
        age={personsState.persons[1].age}
        click={switchNameHandler.bind(this, 'Max!')}
        >
        My Hobbies: Racing
      </Person>
      <Person 
        name={personsState.persons[2].name} 
        age={personsState.persons[2].age}
      />
    </div>
  );
  // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hi, I\'m a React App!!!'));
}

export default app;
```

### Adding Two Way Binding

Person.js
```js
import React from 'react';

const person = ( props ) => {
    return (
        <div>
            <p onClick={props.click}>I'm {props.name} and I am {props.age} years old!</p>
            <p>{props.children}</p>
            <input type="text" onChange={props.changed} value={props.name}/>
        </div>
    )
}

export default person;
```

App.js
```js
import React, { useState } from 'react';
import './App.css';
import Person from './Person/Person.js';

const app = props => {
  const [ personsState, setPersonsState] = useState({
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ]
  });

  const [otherState, setOtherState] = useState('some other value');

  console.log(personsState, otherState);

  const switchNameHandler = (newName) => {
    // console.log('Was clicked!');
    // DON'T DO THIS this.state.persons[0].name = 'Maximilian';
    setPersonsState({
      persons: [
        { name: newName, age: 28 },
        { name: 'Manu', age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }  

  const nameChangedHandler = (event) => {
    setPersonsState({
      persons: [
        { name: 'Max', age: 28 },
        { name: event.target.value, age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }

  return (
    <div className="App">

      <h1>Hi I'm a React App</h1>
      <p>This is really working</p>
      <button onClick={() => switchNameHandler('Maximilian!!!')}>Switch Name</button>
      <Person 
        name={personsState.persons[0].name} 
        age={personsState.persons[0].age}
      />
      <Person 
        name={personsState.persons[1].name} 
        age={personsState.persons[1].age}
        click={switchNameHandler.bind(this, 'Max!')}
        changed={nameChangedHandler}
        >
        My Hobbies: Racing
      </Person>
      <Person 
        name={personsState.persons[2].name} 
        age={personsState.persons[2].age}
      />
    </div>
  );
  // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hi, I\'m a React App!!!'));
}

export default app;
```

### Adding Styling with Stylesheets

Add a `Person.css` file in the folder `react-complete-guide/src/Person/`

Person.css
```css
.Person {
    width: 60%;
    margin: 16px auto;
    border: 1px solid #eee;
    box-shadow: 0 2px 3px #ccc;
    padding: 16px;
    text-align: center;
}
```

Person.js
```js
import React from 'react';

import './Person.css';

const person = ( props ) => {
    return (
        <div className="Person">
            <p onClick={props.click}>I'm {props.name} and I am {props.age} years old!</p>
            <p>{props.children}</p>
            <input type="text" onChange={props.changed} value={props.name}/>
        </div>
    )
}

export default person;
```

### Working with Inline Styles

App.js
```js
import React, { useState } from 'react';
import './App.css';
import Person from './Person/Person.js';

const app = props => {
  const [ personsState, setPersonsState] = useState({
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ]
  });

  const [otherState, setOtherState] = useState('some other value');

  console.log(personsState, otherState);

  const switchNameHandler = (newName) => {
    // console.log('Was clicked!');
    // DON'T DO THIS this.state.persons[0].name = 'Maximilian';
    setPersonsState({
      persons: [
        { name: newName, age: 28 },
        { name: 'Manu', age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }  

  const nameChangedHandler = (event) => {
    setPersonsState({
      persons: [
        { name: 'Max', age: 28 },
        { name: event.target.value, age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }

  const style = {
    backgroundColor: 'white',
    font: 'inherit',
    border: '1px solid blue',
    padding: '8px',
    cursor: 'pointer'
  };

  return (
    <div className="App">

      <h1>Hi I'm a React App</h1>
      <p>This is really working</p>
      <button 
        style={style}
        onClick={() => switchNameHandler('Maximilian!!!')}>Switch Name</button>
      <Person 
        name={personsState.persons[0].name} 
        age={personsState.persons[0].age}
      />
      <Person 
        name={personsState.persons[1].name} 
        age={personsState.persons[1].age}
        click={switchNameHandler.bind(this, 'Max!')}
        changed={nameChangedHandler}
        >
        My Hobbies: Racing
      </Person>
      <Person 
        name={personsState.persons[2].name} 
        age={personsState.persons[2].age}
      />
    </div>
  );
  // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hi, I\'m a React App!!!'));
}

export default app;
```

### Useful Resources & Links

- create-react-app: https://github.com/facebookincubator/create-react-app
- Introducing JSX: https://reactjs.org/docs/introducing-jsx.html
- Rendering Elements: https://reactjs.org/docs/rendering-elements.html
- Components & Props: https://reactjs.org/docs/components-and-props.html
- Listenable Events: https://reactjs.org/docs/events.html

## Working with Lists and Conditionals

### Rendering Content Conditionally

App.js
```js
import React, { Component } from 'react';
import './App.css';
import Person from './Person/Person.js';

class App extends Component {

  state = {
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ],
    otherState: 'some other value',
    showPersons: false
  }

  switchNameHandler = (newName) => {
    // console.log('Was clicked!');
    // DON'T DO THIS this.state.persons[0].name = 'Maximilian';
    this.setState({
      persons: [
        { name: newName, age: 28 },
        { name: 'Manu', age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }  

  nameChangedHandler = (event) => {
    this.setState({
      persons: [
        { name: 'Max', age: 28 },
        { name: event.target.value, age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }

  togglePersonsHandler = () => {
    const doesShow = this.state.showPersons;
    this.setState({showPersons: !doesShow});
  }

  render () {

  const style = {
    backgroundColor: 'white',
    font: 'inherit',
    border: '1px solid blue',
    padding: '8px',
    cursor: 'pointer'
  };

  return (
    <div className="App">

      <h1>Hi I'm a React App</h1>
      <p>This is really working</p>
      <button 
        style={style}
        onClick={this.togglePersonsHandler}>Toggle Persons</button>
      
      { this.state.showPersons ? 
        <div>
          <Person 
            name={this.state.persons[0].name} 
            age={this.state.persons[0].age}
          />
          <Person 
            name={this.state.persons[1].name} 
            age={this.state.persons[1].age}
            click={this.switchNameHandler.bind(this, 'Max!')}
            changed={this.nameChangedHandler}
            >
            My Hobbies: Racing
          </Person>
          <Person 
            name={this.state.persons[2].name} 
            age={this.state.persons[2].age}
          />
        </div> : null
      }
      
    </div>
  );
  // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hi, I\'m a React App!!!'));
}}

export default App;
```

### Handling Dynamic Content "The JavaScript Way"

App.js
```js
import React, { Component } from 'react';
import './App.css';
import Person from './Person/Person.js';

class App extends Component {

  state = {
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ],
    otherState: 'some other value',
    showPersons: false
  }

  switchNameHandler = (newName) => {
    // console.log('Was clicked!');
    // DON'T DO THIS this.state.persons[0].name = 'Maximilian';
    this.setState({
      persons: [
        { name: newName, age: 28 },
        { name: 'Manu', age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }  

  nameChangedHandler = (event) => {
    this.setState({
      persons: [
        { name: 'Max', age: 28 },
        { name: event.target.value, age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }

  togglePersonsHandler = () => {
    const doesShow = this.state.showPersons;
    this.setState({showPersons: !doesShow});
  }

  render () {

  const style = {
    backgroundColor: 'white',
    font: 'inherit',
    border: '1px solid blue',
    padding: '8px',
    cursor: 'pointer'
  };

  let persons = null;

  if (this.state.showPersons) {
    persons = (
      <div>
        <Person 
          name={this.state.persons[0].name} 
          age={this.state.persons[0].age}
        />
        <Person 
          name={this.state.persons[1].name} 
          age={this.state.persons[1].age}
          click={this.switchNameHandler.bind(this, 'Max!')}
          changed={this.nameChangedHandler}
          >
          My Hobbies: Racing
        </Person>
        <Person 
          name={this.state.persons[2].name} 
          age={this.state.persons[2].age}
        />
      </div>
    );
  }

  return (
    <div className="App">

      <h1>Hi I'm a React App</h1>
      <p>This is really working</p>
      <button 
        style={style}
        onClick={this.togglePersonsHandler}>Toggle Persons
      </button>
      {persons} 
    </div>
  );
  // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hi, I\'m a React App!!!'));
}}

export default App;
```

### Outputting Lists

App.js
```js
import React, { Component } from 'react';
import './App.css';
import Person from './Person/Person.js';

class App extends Component {

  state = {
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ],
    otherState: 'some other value',
    showPersons: false
  }

  switchNameHandler = (newName) => {
    // console.log('Was clicked!');
    // DON'T DO THIS this.state.persons[0].name = 'Maximilian';
    this.setState({
      persons: [
        { name: newName, age: 28 },
        { name: 'Manu', age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }  

  nameChangedHandler = (event) => {
    this.setState({
      persons: [
        { name: 'Max', age: 28 },
        { name: event.target.value, age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }

  togglePersonsHandler = () => {
    const doesShow = this.state.showPersons;
    this.setState({showPersons: !doesShow});
  }

  render () {

  const style = {
    backgroundColor: 'white',
    font: 'inherit',
    border: '1px solid blue',
    padding: '8px',
    cursor: 'pointer'
  };

  let persons = null;

  if (this.state.showPersons) {
    persons = (
      <div>
        {this.state.persons.map(person => {
          return <Person 
            name={person.name} 
            age={person.age}/>
        })}
      </div>
    );
  }

  return (
    <div className="App">

      <h1>Hi I'm a React App</h1>
      <p>This is really working</p>
      <button 
        style={style}
        onClick={this.togglePersonsHandler}>Toggle Persons
      </button>
      {persons} 
    </div>
  );
  // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hi, I\'m a React App!!!'));
}}

export default App;
```

### Lists & State

App.js
```js
import React, { Component } from 'react';
import './App.css';
import Person from './Person/Person.js';

class App extends Component {

  state = {
    persons: [
      { name: 'Max', age: 28 },
      { name: 'Manu', age: 29 },
      { name: 'Stephanie', age: 26 }
    ],
    otherState: 'some other value',
    showPersons: false
  }

  nameChangedHandler = (event) => {
    this.setState({
      persons: [
        { name: 'Max', age: 28 },
        { name: event.target.value, age: 29 },
        { name: 'Stephanie', age: 27 }
      ]
    })
  }

  deletePersonHandler = (personIndex) => {
    const persons = this.state.persons;
    persons.splice(personIndex, 1);
    this.setState({persons: persons})
  }

  togglePersonsHandler = () => {
    const doesShow = this.state.showPersons;
    this.setState({showPersons: !doesShow});
  }

  render () {

  const style = {
    backgroundColor: 'white',
    font: 'inherit',
    border: '1px solid blue',
    padding: '8px',
    cursor: 'pointer'
  };

  let persons = null;

  if (this.state.showPersons) {
    persons = (
      <div>
        {this.state.persons.map((person, index) => {
          return <Person 
            click={() => this.deletePersonHandler(index)}
            name={person.name} 
            age={person.age}/>
        })}
      </div>
    );
  }

  return (
    <div className="App">

      <h1>Hi I'm a React App</h1>
      <p>This is really working</p>
      <button 
        style={style}
        onClick={this.togglePersonsHandler}>Toggle Persons
      </button>
      {persons} 
    </div>
  );
  // return React.createElement('div', {className: 'App'}, React.createElement('h1', null, 'Hi, I\'m a React App!!!'));
}}

export default App;
```

### Updating State Immutably

App.js
```js

```
