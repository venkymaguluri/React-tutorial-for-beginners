# React-tutorial-for-beginners
Starting with react(Reference from w3schools.com)


Before starting with React.JS, you should have intermediate experience in:

HTML
CSS
JavaScript
You should also have some experience with the new JavaScript features introduced in ECMAScript 6 (ES6)


What is React?
React is a JavaScript library created by Facebook.
React is a tool for building UI components.

How does React Work?
React creates a VIRTUAL DOM in memory.
Instead of manipulating the browser's DOM directly, React creates a virtual DOM in memory, where it does all the necessary manipulating, before making the changes in the browser DOM.


In order to use create-react-app, you need to have Node.js installed. It's recommended that you use the long-term support (LTS) version. Node includes npm (the node package manager), and npx (the node package runner).

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Install create-react-app by running this command in your terminal:
C:\Users\Your Name>npm install -g create-react-app

Run this command to create a React application named myfirstreact:
C:\Users\Your Name>npx create-react-app myfirstreact

Run this command to move to the myfirstreact directory:
C:\Users\Your Name>cd myfirstreact

Run this command to execute the React application myfirstreact:
C:\Users\Your Name\myfirstreact>npm start

A new browser window will pop up with your newly created React App! If not, open your browser and type localhost:3000 in the address bar.


To get an overview of what React is, you can write React code directly in HTML.

But in order to use React in production, you need NPM and Node.js installed.


Modify the React Application
So far so good, but how do I change the content?

Look in the myfirstreact directory, and you will find a src folder. Inside the src folder there is a file called App.js, open it and try changing the HTML content and save the file.

Notice that the changes are visible immediately after you save the file, you do not have to reload the browser!

--------------------------------------------------------------------------------------------------------------------------------------------

What is ES6?
ES6 stands for ECMAScript 6.

ECMAScript was created to standardize JavaScript, and ES6 is the 6th version of ECMAScript, it was published in 2015, and is also known as ECMAScript 2015.

Why Should I Learn ES6?
React uses ES6, and you should be familiar with some of the new features like:

Classes
Arrow Functions
Variables (let, const, var)



Classes
ES6 introduced classes.

A class is a type of function, but instead of using the keyword function to initiate it, we use the keyword class, and the properties are assigned inside a constructor() method.
You can add your own methods in a class.

Example
A simple class constructor and Create a method named "present":

class Car {
  constructor(name) {
    this.brand = name;
  }
  
  present() {
    return 'I have a ' + this.brand;
  }
}

mycar = new Car("Ford");
mycar.present();

output: I have a Ford

Note: The constructor function is called automatically when the object is initialized.


Class Inheritance
To create a class inheritance, use the extends keyword.


A class created with a class inheritance inherits all the methods from another class:

Example
Create a class named "Model" which will inherit the methods from the "Car" class:

class Car {
  constructor(name) {
    this.brand = name;
  }

  present() {
    return 'I have a ' + this.brand;
  }
}

class Model extends Car {
  constructor(name, mod) {
    super(name);
    this.model = mod;
  }  
  show() {
      return this.present() + ', it is a ' + this.model
  }
}
mycar = new Model("Ford", "Mustang");
mycar.show();

output: I have a Ford, it is a Mustang

By calling the super() method in the constructor method, we call the parent's constructor method and gets access to the parent's properties and methods.


Arrow Functions
Arrow functions were introduced in ES6.

Arrow functions allow us to write shorter function syntax:

Before:
hello = function() {
  return "Hello World!";
}

With Arrow Function:
hello = () => {
  return "Hello World!";
}

It gets shorter! If the function has only one statement, and the statement returns a value, you can remove the brackets and the return keyword:

Arrow Functions Return Value by Default:
hello = () => "Hello World!";


If you have parameters, you pass them inside the parentheses:

Arrow Function With Parameters:
hello = (val) => "Hello " + val;

In fact, if you have only one parameter, you can skip the parentheses as well:

Arrow Function Without Parentheses:
hello = val => "Hello " + val;

What About this?
The handling of this is also different in arrow functions compared to regular functions.

In short, with arrow functions there are no binding of this.

In regular functions the this keyword represented the 'object that called the function', which could be the window, the document, a button or whatever.

With arrow functions, the this keyword always represents the 'object that defined the arrow function'.


# Variables
Before ES6 there were only one way of defining your variables: with the var keyword. If you did not define them, they would be assigned to the global object. Unless you were in strict mode, then you would get an error if your variables were undefined.

Now, with ES6, there are three ways of defining your variables: var, let, and const.

var
var x = 5.6;

If you use var outside of a function, it belongs to the global scope.

If you use var inside of a function, it belongs to that function.

If you use var inside of a block, i.e. a for loop, the variable is still available outside of that block.

# Note:var has a function scope, not a block scope.

let
let x = 5.6;

# Note: let has a block scope.

let is the block scoped version of var, and is limited to the block (or expression) where it is defined.

If you use let inside of a block, i.e. a for loop, the variable is only available inside of that loop

const
const x = 5.6;

const is a variable that once it has been created, its value can never change.

# Note:const has a block scope.

----------------------------------------------------------------------------------------------------------------------------------------------

React Render HTML

React's goal is in many ways to render HTML in a web page.

React renders HTML to the web page by using a function called ReactDOM.render().

The Render Function
The ReactDOM.render() function takes two arguments, HTML code and an HTML element.

The purpose of the function is to display the specified HTML code inside the specified HTML element.

## Example

Display a paragraph inside the "root" element:

ReactDOM.render(<p>Hello</p>, document.getElementById('root'));

The result is displayed in the <div id="root"> element:

<body>

  <div id="root"></div>

</body>


### The HTML Code
The HTML code in this tutorial uses 'JSX' which allows you to write HTML tags inside the JavaScript code:

Example
Create a variable that contains HTML code and display it in the root node:

const myelement = (
  <table>
    <tr>
      <th>Name</th>
    </tr>
    <tr>
      <td>John</td>
    </tr>
    <tr>
      <td>Elsa</td>
    </tr>
  </table>
);

ReactDOM.render(myelement, document.getElementById('root'));


### The Root Node
The root node is the HTML element where you want to display the result.

It is like a container for content managed by React.

It does NOT have to be a <div> element and it does NOT have to have the id='root':
  
  
### Example
The root node can be called whatever you like:

<body>

  <header id="sandy"></header>

</body>
Display the result in the <header id="sandy"> element:

ReactDOM.render(<p>Hallo</p>, document.getElementById('sandy'));



-----------------------------------------------------------------------------------------------------------------------------------------------------------------------
## What is JSX?
JSX stands for JavaScript XML.

JSX allows us to write HTML in React.

JSX makes it easier to write and add HTML in React.


#### Coding JSX

JSX allows us to write HTML elements in JavaScript and place them in the DOM without any createElement()  and/or appendChild() methods.

JSX converts HTML tags into react elements.

You are not required to use JSX, but JSX makes it easier to write React applications.


Example 1       
JSX:

const myelement = <h1>I Love JSX!</h1>;

ReactDOM.render(myelement, document.getElementById('root'));

Example 2     
Without JSX:

const myelement = React.createElement('h1', {}, 'I do not use JSX!');

ReactDOM.render(myelement, document.getElementById('root'));


Expressions in JSX

With JSX you can write expressions inside curly braces { }.

The expression can be a React variable, or property, or any other valid JavaScript expression. JSX will execute the expression and return the result:

Example
Execute the expression 5 + 5:


const myelement = <h1>React is {5 + 5} times better with JSX</h1>;



Inserting a Large Block of HTML
To write HTML on multiple lines, put the HTML inside parentheses:

Example
Create a list with three list items:

const myelement = (
  <ul>
    <li>Apples</li>
    <li>Bananas</li>
    <li>Cherries</li>
  </ul>
);



One Top Level Element

The HTML code must be wrapped in ONE top level element.

So if you like to write two headers, you must put them inside a parent element, like a div element

Example:                                        
Wrap two headers inside one DIV element:

const myelement = (

  <div>
  
    <h1>I am a Header.</h1>
    
    <h1>I am a Header too.</h1>
    
  </div>
  
);


Elements Must be Closed:
JSX follows XML rules, and therefore HTML elements must be properly closed.

Example:

Close empty elements with />

const myelement = <input type="text" />;

JSX will throw an error if the HTML is not properly closed.


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
### React Components
Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML via a render() function.

Components come in two types, Class components and Function components.


Component Constructor

If there is a constructor() function in your component, this function will be called when the component gets initiated.

The constructor function is where you initiate the component's properties.

In React, component properties should be kept in an object called state.


The constructor function is also where you honor the inheritance of the parent component by including the super() statement, which executes the parent component's constructor function, and your component has access to all the functions of the parent component (React.Component).


Example

Create a constructor function in the Car component, and add a color property: and Use the color property in the render() function:

class Car extends React.Component {

  constructor() {
  
    super();
    
    this.state = {color: "red"};
    
  }
  
  render() {
  
    return <h2>I am a {this.state.color} Car!</h2>;
    
  }
  
}


Props

Another way of handling component properties is by using props.

Props are like function arguments, and you send them into the component as attributes.

Use an attribute to pass a color to the Car component, and use it in the render() function:

Example

class Car extends React.Component {

  render() {
  
    return <h2>I am a {this.props.color} Car!</h2>;
    
  }
  
}

ReactDOM.render(<Car color="red"/>, document.getElementById('root'));



Components in Components

We can refer to components inside other components:

Example

Use the Car component inside the Garage component:

class Car extends React.Component {

  render() {
  
    return <h2>I am a Car!</h2>;
    
  }
  
}


class Garage extends React.Component {

  render() {
  
    return (
    
      <div>
      
      <h1>Who lives in my Garage?</h1>
      
      <Car />
      
      </div>
      
    );
    
  }
  
}

ReactDOM.render(<Garage />, document.getElementById('root'));
 


Components in Files

React is all about re-using code, and it can be smart to insert some of your components in separate files.

To do that, create a new file with a .js file extension and put the code inside it:

Note that the file must start by importing React (as before), and it has to end with the statement export default Car;.

Example

This is the new file, we named it "App.js":

import React from 'react';

import ReactDOM from 'react-dom';

class Car extends React.Component {

  render() {
  
    return <h2>Hi, I am a Car!</h2>;
    
  }
  
}

export default Car;
 

To be able to use the Car component, you have to import the file in your application.


 Example
 
Now we import the "App.js" file in the application, and we can use the Car component as if it was created here.

import React from 'react';

import ReactDOM from 'react-dom';

import Car from './App.js';

ReactDOM.render(<Car />, document.getElementById('root'));
 
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## React Props

Props are arguments passed into React components.

Props are passed to components via HTML attributes.

React Props are like function arguments in JavaScript and attributes in HTML.

To send props into a component, use the same syntax as HTML attributes:

Example

Add a "brand" attribute to the Car element:

const myelement = <Car brand="Ford" />;

The component receives the argument as a props object:

Example

Use the brand attribute in the component:

class Car extends React.Component {

  render() {
  
    return <h2>I am a {this.props.brand}!</h2>;
    
  }
  
}


Pass Data

Props are also how you pass data from one component to another, as parameters.

Example

Send the "brand" property from the Garage component to the Car component:

class Car extends React.Component {

  render() {
  
    return <h2>I am a {this.props.brand}!</h2>;
    
  }
  
}

class Garage extends React.Component {

  render() {
  
    return (
    
      <div>
      
      <h1>Who lives in my garage?</h1>
      
      <Car brand="Ford" />
      
      </div>
      
    );
    
  }
  
}

ReactDOM.render(<Garage />, document.getElementById('root'));


If you have a variable to send, and not a string as in the example above, you just put the variable name inside curly brackets:

Example

Create a variable named "carname" and send it to the Car component:

class Car extends React.Component {

  render() {
  
    return <h2>I am a {this.props.brand}!</h2>;
    
  }
  
}

class Garage extends React.Component {

  render() {
  
    const carname = "Ford";
    
    return (
    
      <div>
      
      <h1>Who lives in my garage?</h1>
      
      <Car brand={carname} />
      
      </div>
      
    );
    
  }
  
}

ReactDOM.render(<Garage />, document.getElementById('root'));
 
 

Or if it was an object:

Example

Create an object named "carinfo" and send it to the Car component:

class Car extends React.Component {

  render() {
  
    return <h2>I am a {this.props.brand.model}!</h2>;
  }
  
}


class Garage extends React.Component {

  render() {
  
    const carinfo = {name: "Ford", model: "Mustang"};
    
    return (
    
      <div>
      
      <h1>Who lives in my garage?</h1>
      
      <Car brand={carinfo} />
      
      </div>
      
    );
    
  }
  
}

ReactDOM.render(<Garage />, document.getElementById('root'));


Props in the Constructor

If your component has a constructor function, the props should always be passed to the constructor and also to the React.Component via the super() method.

Example

class Car extends React.Component {

  constructor(props) {
  
    super(props);
    
  }
  render() {
  
    return <h2>I am a {this.props.model}!</h2>;
    
  }
  
}

ReactDOM.render(<Car model="Mustang"/>, document.getElementById('root'));
 
Note: React Props are read-only! You will get an error if you try to change their value.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------

# React State
React components has a built-in state object.

The state object is where you store property values that belongs to the component.

When the state object changes, the component re-renders.

Creating the state Object

The state object is initialized in the constructor:

Example:

Specify the state object in the constructor method:

class Car extends React.Component {

  constructor(props) {
  
    super(props);
    
    this.state = {brand: "Ford"};
    
  }
  
  render() {
  
    return (
    
      <div>
      
        <h1>My Car</h1>
        
      </div>
      
    );
    
  }
  
}


The state object can contain as many properties as you like:

Example:

Specify all the properties your component need:

class Car extends React.Component {

  constructor(props) {
  
    super(props);
    
    this.state = {
    
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
    
  }
  
  render() {
  
    return (
    
      <div>
      
        <h1>My Car</h1>
        
      </div>
      
    );
    
  }
  
}
 
 
 
 Changing the state Object
 
To change a value in the state object, use the this.setState() method.

When a value in the state object changes, the component will re-render, meaning that the output will change according to the new value(s).

Example:

Add a button with an onClick event that will change the color property:

class Car extends React.Component {

  constructor(props) {
  
    super(props);
    
    this.state = {
    
      brand: "Ford",
      model: "Mustang",
      color: "red",
      year: 1964
    };
    
  }
  
  changeColor = () => {
  
    this.setState({color: "blue"});
    
  }
  
  render() {
  
    return (
    
      <div>
      
        <h1>My {this.state.brand}</h1>
        
        <p>
        
          It is a {this.state.color}
          
          {this.state.model}
          
          from {this.state.year}.
          
        </p>
        
        <button
        
          type="button"
          
          onClick={this.changeColor}
          
        >Change color</button>
        
      </div>
      
    );
    
  }
  
} 
 

Always use the setState() method to change the state object, it will ensure that the component knows its been updated and calls the render() method (and all the other lifecycle methods).
 
------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 

# React Lifecycle
Lifecycle of Components

Each component in React has a lifecycle which you can monitor and manipulate during its three main phases.

The three phases are: __Mounting, Updating, and Unmounting.__

#### Mounting
__Mounting means putting elements into the DOM.__

React has four built-in methods that gets called, in this order, when mounting a component:

1. constructor()

1. getDerivedStateFromProps()

1. render()

1. componentDidMount()

The render() method is required and will always be called, the others are optional and will be called if you define them.


__constructor

The constructor() method is called before anything else, when the component is initiated, and it is the natural place to set up the initial __state__ and other initial values.

The constructor() method is called with the __props__, as arguments, and you should always start by calling the __super(props)__ before anything else, this will initiate the parent's constructor method and allows the component to inherit methods from its parent (__React.Component__).

Example:

The constructor method is called, by React, every time you make a component:

''' react
class Header extends React.Component {
  constructor(props) {
    super(props);
    this.state = {favoritecolor: "red"};
  }
  render() {
    return (
      <h1>My Favorite Color is {this.state.favoritecolor}</h1>
    );
  }
}

'''
ReactDOM.render(<Header />, document.getElementById('root'));

__getDerivedStateFromProps

The getDerivedStateFromProps() method is **called right before rendering the element(s) in the DOM**.

This is the natural place to set the __state__ object based on the initial props.

It takes __state__ as an argument, and returns an object with changes to the __state__.

__Example:

The getDerivedStateFromProps method is called right before the render method:

''' react
class Header extends React.Component {
  constructor(props) {
    super(props);
    this.state = {favoritecolor: "red"};
  }
  static getDerivedStateFromProps(props, state) {
    return {favoritecolor: props.favcol };
  }
  render() {
    return (
      <h1>My Favorite Color is {this.state.favoritecolor}</h1>
    );
  }
}

ReactDOM.render(<Header favcol="yellow"/>, document.getElementById('root'));
'''

__render__

The render() method is required, and is the method that actually __outputs the HTML to the DOM__.

__Example:__

A simple component with a simple render() method:

''' react
class Header extends React.Component {
  render() {
    return (
      <h1>This is the content of the Header component</h1>
    );
  }
}

ReactDOM.render(<Header />, document.getElementById('root'));
'''

__componentDidMount__

The componentDidMount() method is __called after the component is rendered__.

This is where you run statements that requires that the component is already placed in the DOM.

Example:
At first my favorite color is red, but give me a second, and it is yellow instead:

''' react
class Header extends React.Component {
  constructor(props) {
    super(props);
    this.state = {favoritecolor: "red"};
  }
  componentDidMount() {
    setTimeout(() => {
      this.setState({favoritecolor: "yellow"})
    }, 1000)
  }
  render() {
    return (
      <h1>My Favorite Color is {this.state.favoritecolor}</h1>
    );
  }
}

ReactDOM.render(<Header />, document.getElementById('root'));
'''

#### Updating

The next phase in the lifecycle is __when a component is updated__.

A component is __updated whenever there is a change in the component's state or props.

React has __five built-in methods__ that gets called, in this order, when a component is updated:

1. getDerivedStateFromProps()
1. shouldComponentUpdate()
1. render()
1. getSnapshotBeforeUpdate()
1. componentDidUpdate()

The __render()__ method is __required and will always be called__, the others are optional and will be called if you define them.



#### Unmounting

The next phase in the lifecycle is __when a component is removed from the DOM__, or unmounting as React likes to call it.

React has only one built-in method that gets called when a component is unmounted:

__componentWillUnmount()__

##### componentWillUnmount
The componentWillUnmount method is called when the component is about to be removed from the DOM.
----------------------------------------------------------------------------------------------------------------------------------------------------------------

## React Events

Just like HTML, React can __perform actions based on user events__.

React has the same events as HTML: __click, change, mouseover etc.

__Adding Events__

React events are written in camelCase syntax:

__onClick__ instead of __onclick__.

React event handlers are written inside curly braces:

__onClick={shoot}__  instead of __onClick="shoot()"__.

React:

'''react
<button onClick={shoot}>Take the Shot!</button>
'''

HTML:

'''HTML
<button onclick="shoot()">Take the Shot!</button>
'''

#### Event Handlers
A good practice is to put the event handler as a method in the component class:

Example:
Put the shoot function inside the Football component:

'''
class Football extends React.Component {
  shoot() {
    alert("Great Shot!");
  }
  render() {
    return (
      <button onClick={this.shoot}>Take the shot!</button>
    );
  }
}

ReactDOM.render(<Football />, document.getElementById('root'));
'''

#### Bind this
__For methods__ in React, the __this keyword should represent the component that owns the method__.

That is why you should use arrow functions. With arrow functions, this will always represent the object that defined the arrow function.

__Why Arrow Functions?

In class components, the this keyword is not defined by default, so with __regular functions the this keyword represents the object that called the method__, which can be the __global window object, a HTML button, or whatever__.

Read more about binding this in our React ES6 'What About this?' chapter.

If you use regular functions instead of arrow functions you have to bind this to the component instance using the bind() method:

