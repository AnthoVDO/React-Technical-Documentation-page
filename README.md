# React technical documentation page.

The purpose of this project is to complet the 4th project of the Free Code Camp Responsive Web Design Projects - Build a Technical Documentation Page.

All the text inside is made to make the project more real.

Please check the reference if your are interrested about the subject.

This project will be also available on codepen.io

## Tool

To do this page, I will use HTML, CSS.

## Color Code

    --bodyBackGround: #3e4049;
    --mainBackGround: #212227;
    --mainTxtColor: #FFFFFf;
    --menuBackGround: #7a7887;
    --menuBackGroundSection: #50B6FF;
    --codeBackGround: #0b253C;
    --codeColor: #009CA6;
    --headerCodeBackGround: #041a2c;
    --menuBackGroundMain: #656472;


## Text bruto

Introduction (https://www.cognitiveclouds.com/insights/what-is-the-difference-between-react-js-and-react-native/)
React.js was developed by Facebook to address its need for a dynamic and high performing User Interface(UI). In 2011, Jordan Walke and his team from Facebook released the React JS library, a JavaScript library which brought together the speed of JavaScript and a new way of rendering pages, leading to a responsive and dynamic user input. In 2015, two years after the team open sourced React.js and its popularity grew, they released React Native.
Declarative (https://en.reactjs.org/)
React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes.
Declarative views make your code more predictable and easier to debug.
Component-Based
Build encapsulated components that manage their own state, then compose them to make complex UIs.
Since component logic is written in JavaScript instead of templates, you can easily pass rich data through your app and keep state out of the DOM.
Difference between React.js and react native (https://www.cognitiveclouds.com/insights/what-is-the-difference-between-react-js-and-react-native/ )
React.js
React.js often referred to as React or ReactJS is a JavaScript library responsible for building a hierarchy of UI components or in other words, responsible for the rendering of UI components. It provides support for both frontend and server-side.
React Native
React Native is a framework for building native applications using JavaScript. React Native compiles to native app components, which makes it possible for you to build native mobile applications. In React JS, React is the base abstraction of React DOM for the web platform, while with React Native, React is still the base abstraction but of React Native. So the syntax and workflow remain similar, but the components are different.
Prerequisites
Using React require minimum knowledge in HTML and Javascript. If you come from differents language, a minimum knowledge in the programming concepts like function, objects, arrays and classes is needed.
Way of working(https://www.taniarascia.com/getting-started-with-react/)
Creat React App
Facebook has created Create React App, an environment that comes pre-configured with everything you need to build a React app. It will create a live development server, use Webpack to automatically compile React, JSX, and ES6, auto-prefix CSS files, and use ESLint to test and warn about mistakes in the code.
To set up create-react-app, run the following code in your terminal, one directory up from where you want the project to live.
$ npx create-react-app react-tutorial
Once that finishes installing, move to the newly created directory and start the project.
$ cd react-tutorial && npm start
Once you run this command, a new window will popup at localhost:3000 with your new React app.
 
If you look into the project structure, you'll see a /public and /src directory, along with the regular node_modules, .gitignore, README.md, and package.json.
In /public, our important file is index.html, which is very similar to the static index.html file we made earlier - just a root div. This time, no libraries or scripts are being loaded in. The /src directory will contain all our React code.
To see how the environment automatically compiles and updates your React code, find the line that looks like this in /src/App.js:
To get started, edit `src/App.js` and save to reload.
And replace it with any other text. Once you save the file, you'll notice localhost:3000 compiles and refreshes with the new data.
Go ahead and delete all the files out of the /src directory, and we'll create our own boilerplate file without any bloat. We'll just keep index.css and index.js.
For index.css, I just copy-and-pasted the contents of Primitive CSS into the file. If you want, you can use Bootstrap or whatever CSS framework you want, or nothing at all.
Now in index.js, we're importing React, ReactDOM, and the CSS file.
src/index.js
import React from 'react'
import ReactDOM from 'react-dom'
import './index.css'
Lets creat an App component.
Let's add a div element with a class. We will use className instead of class.
src/index.js
class App extends React.Component {
  render() {
    return (
      <div className="App">
        <h1>Hello, React!</h1>
      </div>
    )
  }
}
Now, we'll render the App to the root
src/index.js
ReactDOM.render(<App />, document.getElementById('root'))
Here is the full index.js. It is set as a Component as a property of React.
src/index.js
import React, {Component} from 'react'
import ReactDOM from 'react-dom'
import './index.css'
class App extends Component {
  render() {
    return (
      <div className="App">
        <h1>Hello, React!</h1>
      </div>
    )
  }
}
ReactDOM.render(<App />, document.getElementById('root'))
If you go back to localhost:3000, you'll see "Hello, React!".
Now, we have the beginning of a React app.
React Developer Tools
There is an extension called React Developer Tools that will make your life much easier when working with React. Download React DevTools for Chrome, or whatever browser you prefer to work on.
After you install it, when you open DevTools, you'll see a tab for React. Click on it, and you'll be able to inspect components as they're written. You can still go to the Elements tab to see the actual DOM output. It may not seem like that much of a deal now, but as the app gets more complicated, it will become increasingly necessary to use.
 
Now we have all the tools and setup we need to actually begin working with React.
JSX: JavaScript + XML
As you've seen, we've been using what looks like HTML in our React code, but it's not quite HTML. This is JSX, which stands for JavaScript XML.
With JSX, we can write what looks like HTML, and also we can create and use our own XML-like tags. Here's what JSX looks like assigned to a variable.
JSX
const heading = <h1 className="site-heading">Hello, React</h1>
Using JSX is not mandatory for writing React. Under the hood, it's running createElement, which takes the tag, object containing the properties, and children of the component and renders the same information. The below code will have the same output as the JSX above.
No JSX
const heading = React.createElement('h1', {className: 'site-heading'}, 'Hello, React!')
JSX is actually closer to JavaScript, not HTML, so there are a few key differences to note when writing it.
    className is used instead of class for adding CSS classes, as class is a reserved keyword in JavaScript.
    Properties and methods in JSX are camelCase - onclick will become onClick.
    Self-closing tags must end in a slash - e.g. <img />

JavaScript expressions can also be embedded inside JSX using curly braces, including variables, functions, and properties.
const name = 'Tania'
const heading = <h1>Hello, {name}</h1>
JSX is easier to write and understand than creating and appending many elements in vanilla JavaScript, and is one of the reasons people love React so much.
Components
Almost everything in React consists of components, which can be class components or simple components.
Most React apps have many small components, and everything loads into the main App component. Components also often get their own file.
The class component can be created to be used multiple time.
The simple component is a function. This component doesn't used the class keyword.
Props
One of the big deals about React is how it handles data, and it does so with properties, referred to as props, and with state.
State
if we want to be able to delete an item from the array. With props, we have a one way data flow, but with state we can update private data from a component.
You can think of state as any data that should be saved and modified without necessarily being added to a database - for example, adding and removing items from a shopping cart before confirming your purchase.
Go further
If you want to go further with React, I recommand to follow this 2 links 
Getting started with React
(https://www.taniarascia.com/getting-started-with-react/) 
Reactjs.org
https://en.reactjs.org/
Reference
1) https://www.cognitiveclouds.com/insights/what-is-the-difference-between-react-js-and-react-native/
2) https://en.reactjs.org/
3) https://www.taniarascia.com/getting-started-with-react/


