# Reading Notes for Class 03

## Lifting State UP

- often, several components need to reflect the same changing data

- this takes celsius as a prop and prints whether it is enough to boil water

```js
function BoilingVerdict(props) {
  if (props.celsius >= 100) {
    return <p>The water would boil.</p>;
  }
  return <p>The water would not boil.</p>;
}
```

- this renders an input that lets you enter the temp and keep its value in the stat

``` js
class Calculator extends React.Component {
  constructor(props) {
    super(props);
    this.handleChange = this.handleChange.bind(this);
    this.state = {temperature: ''};
  }

  handleChange(e) {
    this.setState({temperature: e.target.value});
  }

  render() {
    const temperature = this.state.temperature;
    return (
      <fieldset>
        <legend>Enter temperature in Celsius:</legend>
        <input
          value={temperature}
          onChange={this.handleChange} />
        <BoilingVerdict
          celsius={parseFloat(temperature)} />
      </fieldset>
    );
  }
}
```
### Adding a second input to this

- want to add Farenheit

1. extract TemperatureInput component from **calculator**

2. add a new scale prop to it that can be 'c' or 'f'

``` js
const scaleNames = {
  c: 'Celsius',
  f: 'Fahrenheit'
};

class TemperatureInput extends React.Component {
  constructor(props) {
    super(props);
    this.handleChange = this.handleChange.bind(this);
    this.state = {temperature: ''};
  }

  handleChange(e) {
    this.setState({temperature: e.target.value});
  }

  render() {
    const temperature = this.state.temperature;
    const scale = this.props.scale;
    return (
      <fieldset>
        <legend>Enter temperature in {scaleNames[scale]}:</legend>
        <input value={temperature}
               onChange={this.handleChange} />
      </fieldset>
    );
  }
}
```

- THe calculator can render to seperate inputs

```js
class Calculator extends React.Component {
  render() {
    return (
      <div>
        <TemperatureInput scale="c" />
        <TemperatureInput scale="f" />
      </div>
    );
  }
}
```

### Converting the celsius to F and back

``` js
function toCelsius(fahrenheit) {
  return (fahrenheit - 32) * 5 / 9;
}

function toFahrenheit(celsius) {
  return (celsius * 9 / 5) + 32;
}
```

### lifting state up

- both TemperatureInput keep their values in the local state

- in order to share and be in sync with eachother, we need to move TemperatureInput from **local state** and put it in the parent (of both) component: ***CALCULATOR***

``` js
  render() {
    // Before: const temperature = this.state.temperature;
    const temperature = this.props.temperature;
    // ...
```

### Lessons learned

1. THERE SHOULD BE A SINGLE SOURCE OF TRUTH FOR ANY DATA THAT CHANGES IN REACT

2. if something can be derived from either props or in state, it **SHOULD NOT** be in state

## Lists and Keys

- in React, transforming arrays into lists of elements is very similar to push a new array.map

### Rendering Multiple Components:

- you can build collections of elements and include them in JSX using {}

- you can assign items to lists

```js
const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
)
```

- THen, render it to the DOM

```js
ReactDOM.render(
  <ul>{listItems}</ul>,
  document.getElementById('root')
);
```

### Basic List Component

- usually you would render lists in a **Component**

- This accepts an array of numbers and outputs a list

```js
function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    <li key={number.toString()}>
      {number}
    </li>
  );
  return (
    <ul>{listItems}</ul>
  );
}

const numbers = [1, 2, 3, 4, 5];
ReactDOM.render(
  <NumberList numbers={numbers} />,
  document.getElementById('root')
);
```

- HAVE TO ASSIGN KEY for it to work for this ex.

### Keys

- Keys help react identify which items have changed, are added, or removed

- best way to get a key is to use a string that uniquely identifies a list item

### Extracting Components with keys

- keys only make sense in the context of the surrounding aray. 

### Keys must only be unique among siblings

- keys used within arrays should be unique among their siblings, but don't need to be globally unique. 

- We can use the same key for different arrays

- keys serve as a hint to React, but they don't get passed to your components (THEY ARE NOT PASSED PROPS)

### Embedding map() in JSX

- JSX allows embedding any expression in curly braces to we could inline map()

```js
function NumberList(props) {
  const numbers = props.numbers;
  return (
    <ul>
      {numbers.map((number) =>
        <ListItem key={number.toString()}
                  value={number} />
      )}
    </ul>
  );
}
```

## The Spread Operator

- useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a functions arguments

### What is the spread?

- the spread syntax is represented with ***...***

- EX ...arr

```js
Math.max(1,3,5) // 5
Math.max([1,3,5]) // NaN
```

- this will produce NAN

- using ... will spread it into seperate arguments

```js
Math.max(...[1,3,5]) // 5
```

### What else can it do?

1. copy an array
2. combine an array
3. use math functions
4. using an array as arguments
5. adding an item to a list
6. adding to state in React
7. Combining objects
8. Converting NodeList to and array

### A great example

```js
[...["😋😛😜🤪😝"]] // Array [ "😋😛😜🤪😝" ]
[..."🙂🙃😉😊😇🥰😍🤩!"] // Array(9) [ "🙂", "🙃", "😉", "😊", "😇", "🥰", "😍", "🤩", "!" ]

const hello = {hello: "😋😛😜🤪😝"}
const world = {world: "🙂🙃😉😊😇🥰😍🤩!"}

const helloWorld = {...hello,...world}
console.log(helloWorld) // Object { hello: "😋😛😜🤪😝", world: "🙂🙃😉😊😇🥰😍🤩!" }
```

## Sources

![React Documents](https://reactjs.org/docs/lifting-state-up.html)
![React Documents](https://reactjs.org/docs/lists-and-keys.html)
![medium](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)
