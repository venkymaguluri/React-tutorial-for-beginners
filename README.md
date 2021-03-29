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


Variables
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

# let has a block scope.

let is the block scoped version of var, and is limited to the block (or expression) where it is defined.

If you use let inside of a block, i.e. a for loop, the variable is only available inside of that loop

const
const x = 5.6;

const is a variable that once it has been created, its value can never change.

# Note:const has a block scope.




