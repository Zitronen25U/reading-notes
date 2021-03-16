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

>class Clock extends React.Component {
>render() {
>return (
><div>
><h1>Hello, world!</h1>
><h2>It is {this.props.date.toLocaleTimeString()}.</h2>
></div>
>);
>}
>}

