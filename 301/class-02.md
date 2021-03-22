# Reading Notes for Class 02

## State and Lifecycle:

- we have only used ReactDOM.render() to render previously

### Converting a function to a Class

- 5 SIMPLE STEPS

1. Create an ES6 class, with the same name that extends React.Component.

2. add a single empty method to it called render()

3. move the body of the function into the render() method

4. Replace props with this.props in the render() body

5. Delete the remaining empty function declaration

### Adding lifecycle methods to a class

- "mounting" in react is setting a thing up to be used everytime something else is rendered

- "unmounting" is clearing that thing

- componentDidMount()
  - runs after the component output has been rendered to the DOM

- componentWIllUnmount()
  - will tear down the method

### Using state Correctly

- three things to know about **setState()**

1. Do Not Modify State Directly
  only place you can use setState is a **constructor**

2. State updates may be Asynchronous
  react may batch multiple **setState()** calls into a single update for performance

  because this.props and this.state may be updated, you should ***NOT*** rely on their values for calculating next state
3. State updates are Merged
  react merges the object you provide when setState() is called

### The Data FLows Down

- this is called a top-down data flow

## Handling Events

- react events are named using camelCase

- with JSX you pass a function as the event handler rather than a string

- in HTML normall, it could be

> <botton onclick="activeLaser()">Activate Laser</button>

- in react

> <button onClick={activateLasers}>Activate Lasers</button>

- **Cannot return false to prevent default behavior in react**

- must call ***preventDefault()*** explicitly

### When using react, you generally don't need to call addEventListner

- instead, just provide a listener when the element is intially rendered

- a common patter in ES6 class is for an event handler to be a method on the class
  - ex, Toggle component renders a button that lets the user toggle between "on" and "off"

- you have to be careful about using this in JSX callbacks.
  - in JS, class methods are not bound by default
    - if you forget to bind, it will be undefined when the function is called

- You should always bind methods

### Passing Arguments to Event Handlers

- Inside a loop, it is common to want to pass an extra param to an event handler

-EXAMPLE
  > <button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
  > <button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>

- both are equivalent and use arrow functions

- in both cases, the **e** argument (ract event) will be passed as a second argument after the ID
- with bind, the argument is automatically forwarded (instead of intially declaring and assigning it)

## React Bootstrat Documentation

- what is it?
  - "React-Bootstrap replaces the Bootstrap JavaScript. Each component has been built from scratch as a true React component, without unneeded dependencies like jQuery."

- best way to consume React-Bootsrap is the npm (or yarn)

> npm install react-bootsrtap bootsrap

### importing components

- import xxxxx from 'react-bootsrap/xxxxx

- Theres so many things you can import
  - css
  - Sass
  - custom buttons and etc

### Customizing Bootsrtap

- if you want to customize the variables in bootsrap, you can create a custom Sass file

## Netflify

- uhm, looks freaking amazing

1. connect rep
2. add your build settings
3. deploy website

[Return!](/class301main.md)
