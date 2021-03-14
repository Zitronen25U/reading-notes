# Reading Notes for Class 01!

## Intro to React:

- What is React
  - a declarative, efficient, and flexible JS library for building UI's
  - compose complex UI's from "components"

- has a few types of components

- > React.Component 

- a component takes paramaters called **PROPS** (properties) and returns a display via **render** method

- render returns a description of what you want to see on the screen

- React takes that description and displays the result

- I MADE A TIC TAC TOE GAME with the tutorial!

## Hello World:

- smallest react example

> ReactDOM.render(
  <h1> Hello, world!</h1>
  document.getElementById('root')
);

- this displays hello world on the page

## Introducing JSX

- JSX may look like a template language, but it is actually full JS

- JSX produces React "elements" 

### Why JSX?

- instead of seperating layout and logic in seperate filex, JSX **COMPONENTS** do both.

- React doesn't require JSX, but most find it helpful as a visual aid when working with UI inside JS.

- handles errors better as well. 

- you can embed JSX inside of expressions

- JSX can be an expression too
  - **can use JSX inside of if and for loops**

- can use quotes to specify string literals as attributes

- can use curly braces to embed a JS expression in an attribute
  - >const element = <img src={user.avatarUrl}></img>;

### Specifying Children with JSX

- if a tage is empty, you can close it with the />

- > <img src = {blah.blahURL} /> 
  - will close IMG tag

- JSX tages may contain children

> const element = (
  <div>
    <h1>Hello!</h1>
    <h2>Good to see you here.</h2>
  </div>
);

### JSX prevents injection attacks

- React DOM escapes any values embedded in JSX before rendering

- ensures you cannot inject anything thats not written in your applicaiton

### JSX Represents Objects

- **BABEL** compiles JSX down to React.createElement() calls

> const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);

- preforms a few checks to help you write bug free code

- the above code creats an h1 tag, with a class of 'greeting' and the text of 'Hello, world'

## Rendering Elements- React

- elements are the smallest building blocks of React

- React elements are **immutable**. It's children and attributes cannot be changed. 

- only way to update the UI is to create a new element and pass it to **ReactDOM.render()**

## Components and Props

- elements can also prepresent user-defined components:

> const element = <Welcome name="Sara" />;

- when React sees an element as a user-defined component, it passes JSX attributes and children to this component as a simgle object
  - a **PROP**

- **ALWAYS START COMPONENT NAMES WITH A CAPITAL LETTER**
  - React will treat anything with a lowercase as a DOM tag

### Props are Read-Only

- whether you declare a component as a function or a class, it must never modify its own props

- React has a very strict rule
  - **All React components must act like pure functions with respect to their props.**

[Return Home!](/class301main.md)
